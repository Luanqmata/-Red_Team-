
# Conectando no Banco de Dados (Parte mais chata)

```bash
sudo apt install postgresql postgresql-contrib &&
sudo service postgresql start

msfdb init
```

## Dentro do MSFCONSOLE

```bash
msfconsole
db_connect msf:msf@127.0.0.1:5432/msf
```

---

## Criando Workspace desse Computador

![Criando Workspace](https://github.com/user-attachments/assets/c79ab59f-974d-4781-bb66-693c1e4cff30)

## Serviços

![Serviços](https://github.com/user-attachments/assets/e2602863-3e4e-426a-a54a-eca74d17c896)

## Informações de Host

![Informações de Host](https://github.com/user-attachments/assets/121e0dc0-f0ed-43af-81b0-7d5af6a9aaee)

## Procurando Diretórios Escondidos

![Diretórios Escondidos](https://github.com/user-attachments/assets/f4ec5416-ea24-4f5a-8234-1894a40596b9)

## Aprofundando (  scanner/smb/smb_version  |  scanner/rdp/rdp_scanner  )

![Profundando 2](https://github.com/user-attachments/assets/fdf0e3c5-cae1-4044-a42e-541c8ab3ced3)
![image](https://github.com/user-attachments/assets/d5d2abe2-15f3-42d0-9437-a090990f9c7c)
### Mais info da vuln 512 https://github.com/rapid7/metasploit-framework/blob/master/documentation/modules/auxiliary/scanner/rservices/rexec_login.md

## aprofundando 2 buscando informaçoes de configuração do tomcat do servidor
![image](https://github.com/user-attachments/assets/726cf174-445b-4100-9335-f7e22c518ec0)

---
# INVASÕES
192.168.100.148  21    tcp    ftp          open   vsftpd 2.3.4
![image](https://github.com/user-attachments/assets/abc64304-25ad-45f5-97ee-bf44b724ac86)

## Depois de conseguir acesso como root usando o payload ( Salvar sessão ):

```bash
CTRL + Z
Y

sessions        # Ver sessões ativas
sessions -i 2   # Acessar a sessão 2
```

![image](https://github.com/user-attachments/assets/ea3a1675-41b7-4832-b96c-d626c48420bb)

---

# IVASÂO 2 
192.168.100.148  23    tcp    telnet       open   Linux telnetd
![image](https://github.com/user-attachments/assets/e4a966e1-1675-47cf-8bb2-ee265cab82af)
![image](https://github.com/user-attachments/assets/31a8001f-1199-465d-85a2-9b2c498c04dc)
como pode se notar ele encontrou 2 credenciais validas das criadas usei os logins do rexecbrute do nmap p512 porem só 2 teve resultado positivo 
![image](https://github.com/user-attachments/assets/86525351-ef9c-41b0-bcb0-f11850590a0b)
Checkando se salvou no sessions e esta tudo ok sessoes salvas 

---

# invasão 3
192.168.100.148  5900  tcp    vnc          open   VNC protocol 3.3
![image](https://github.com/user-attachments/assets/9d38a130-a67f-4ce4-9d6a-7e482ed638e9)
![image](https://github.com/user-attachments/assets/7c60bfc9-56b7-4b30-be68-4c3d7ee0a80f)

## obtive a resposta do scan que a as credenciais são ( :password ) agora testar
![image](https://github.com/user-attachments/assets/13f27e69-31e1-442f-ada7-f8adc2eab30d)
![image](https://github.com/user-attachments/assets/bdaccf4b-6405-4f56-a9f0-cfe403ceb4ab)


## Força Bruta com Nmap e Hydra

```bash

# Depois:
hydra -L /home/luan/Desktop/porta_512_logins/usuarios_512.txt \
      -P /home/luan/Desktop/porta_512_logins/passwd_512.txt \
      -vV 192.168.100.102 rexec
```
