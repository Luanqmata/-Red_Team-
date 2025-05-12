# 📦 Conectando no Banco de Dados (Parte mais chata)

```bash
sudo apt install postgresql postgresql-contrib &&
sudo service postgresql start

msfdb init
```

## 💻 Dentro do MSFCONSOLE

```bash
msfconsole
db_connect msf:msf@127.0.0.1:5432/msf
```

---

## 🗂️ Criando Workspace desse Computador

![Criando Workspace](https://github.com/user-attachments/assets/c79ab59f-974d-4781-bb66-693c1e4cff30)

# Exploração da Máquina — Metasploitable 2

## Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1T6XcA_A--FMGiI9jP0G8Lij6B2kIaHFi/view?usp=classroom_web&authuser=0)

## 🛠️ Serviços

![Serviços](https://github.com/user-attachments/assets/e2602863-3e4e-426a-a54a-eca74d17c896)

## 🌐 Informações de Host

![Informações de Host](https://github.com/user-attachments/assets/121e0dc0-f0ed-43af-81b0-7d5af6a9aaee)

## 🔍 Procurando Diretórios Escondidos

![Diretórios Escondidos](https://github.com/user-attachments/assets/f4ec5416-ea24-4f5a-8234-1894a40596b9)

## 🧠 Aprofundando (scanner/smb/smb_version | scanner/rdp/rdp_scanner)

![Profundando 2](https://github.com/user-attachments/assets/fdf0e3c5-cae1-4044-a42e-541c8ab3ced3)
![image](https://github.com/user-attachments/assets/d5d2abe2-15f3-42d0-9437-a090990f9c7c)

🔗 [Mais info da vuln 512](https://github.com/rapid7/metasploit-framework/blob/master/documentation/modules/auxiliary/scanner/rservices/rexec_login.md)

## 📁 Aprofundando 2: Buscando configurações do Tomcat

![image](https://github.com/user-attachments/assets/726cf174-445b-4100-9335-f7e22c518ec0)

---

# 💥 INVASÕES

### 🔓 FTP - 192.168.100.148:21

```text
ftp          open   vsftpd 2.3.4
```

![image](https://github.com/user-attachments/assets/abc64304-25ad-45f5-97ee-bf44b724ac86)

#### Após obter acesso root com payload (salvar sessão):

```bash
CTRL + Z
Y

sessions        # Ver sessões ativas
sessions -i 2   # Acessar a sessão 2
```

![image](https://github.com/user-attachments/assets/ea3a1675-41b7-4832-b96c-d626c48420bb)

---

### 🔓 INVASÃO 2 - Telnet - 192.168.100.148:23

```text
telnet       open   Linux telnetd
```

![image](https://github.com/user-attachments/assets/e4a966e1-1675-47cf-8bb2-ee265cab82af)
![image](https://github.com/user-attachments/assets/31a8001f-1199-465d-85a2-9b2c498c04dc)

> Foram encontradas 2 credenciais válidas criadas via brute force (rexecbrute do Nmap na porta 512).

![image](https://github.com/user-attachments/assets/86525351-ef9c-41b0-bcb0-f11850590a0b)

📌 Verificado que sessões foram salvas com sucesso.

---

### 🔓 INVASÃO 3 - VNC - 192.168.100.148:5900

```text
vnc          open   VNC protocol 3.3
```

![image](https://github.com/user-attachments/assets/9d38a130-a67f-4ce4-9d6a-7e482ed638e9)
![image](https://github.com/user-attachments/assets/7c60bfc9-56b7-4b30-be68-4c3d7ee0a80f)

> Credenciais identificadas: `:password`

![image](https://github.com/user-attachments/assets/13f27e69-31e1-442f-ada7-f8adc2eab30d)
![image](https://github.com/user-attachments/assets/bdaccf4b-6405-4f56-a9f0-cfe403ceb4ab)

### 🔓 INVASÃO 4 - unreal_irc - 192.168.100.148:6667 - Via shell reverse

> Configurações do mf6, E o netcat no meu Windows escutando a resposta do mf6 usando o payload unix/reverse

![image](https://github.com/user-attachments/assets/0f163124-4e0a-42f4-b2d5-dab3ced3daee)
![image](https://github.com/user-attachments/assets/c846313e-8347-48a4-a2c1-73bae76df953)

> Consegui o acesso a máquina, porém o payload que eu usei é muito fraco e não possui um cmd interativo que me retorna as respostas, mas o acesso foi concedido.

>Fazendo uma breve pesquisa com o GPT encontrei um possível payload interativo, testei e consegui um terminal um pouco mais interativo

![image](https://github.com/user-attachments/assets/fc26b3f3-a551-44df-aca3-335c7acf8a8b)

> Shell subido

![image](https://github.com/user-attachments/assets/f5e6f216-0ae9-4e78-8f18-6b5f654475f6)
>

### 🔓 INVASÃO 5 - VNC - 192.168.100.148:5900 - Via shell reverse

> Depois de ter conseguido acesso de root pelo vnc viewr da para dar uma brincada instalando um nc para um reverse shell
![image](https://github.com/user-attachments/assets/78f40755-9145-44bd-8188-b7b7747e5bf4)
>
> Obs: o netcat não estava instalado antes... ai ta constando como sem upgrades, instalei antes da print
> 
> Vamos colocar um para falar e o outro para escutar ,e executar o comando dentro do vncviewer 
![image](https://github.com/user-attachments/assets/573cd44b-d39d-4d0b-9a54-1553842ae82d)
>
![image](https://github.com/user-attachments/assets/d20db048-b0ce-4c90-8a4a-f74d2286d657)
>
> Conseguindo assim ter acesso a arquivos sensiveis como shadow e passwd:
![image](https://github.com/user-attachments/assets/557f278f-89a4-47d8-a5ef-5d240182fd02)
![image](https://github.com/user-attachments/assets/49f8cb3e-7ddb-40ab-a9f4-fe3e43614e45)
>

### 🔓 Quebrando senhas Shadow

> Depois de coseguir acesso ao arquivo de shadow's , vamos pegar a senhas que ainda estao ativas ( sem * ou ! significa que ou nao tem senha pra quebrar ou aquela senha nao existe mais )
>
> Vamos criar um arquivo hash.txt e colocar as hashs que sao quebraveis dentro dele
![image](https://github.com/user-attachments/assets/74d7d11b-9fa5-4238-a988-5ac5e9d99bc5)
>
> Executar o jhon para a quebra das hashs e tambem o hashcat
>
![image](https://github.com/user-attachments/assets/42bab695-39af-4b06-b33f-c85261b852e8)
![image](https://github.com/user-attachments/assets/d32f0ad3-3eef-4ec4-bca9-cf60c5e9ce8f)
> o Jhon nao conseguio quebrar algumas senhas mas o hashcat conseguiu:
> sys:batman
> klog:12345678
> service:service

## 🧪 Força Bruta com Nmap e Hydra

```bash
hydra -L /home/luan/Desktop/porta_512_logins/usuarios_512.txt \
      -P /home/luan/Desktop/porta_512_logins/passwd_512.txt \
      -vV 192.168.100.102 rexec
```
