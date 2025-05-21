# 🛡️ Exploração da Máquina — 0ff3ns!v3 S3cur!ty - Sw4gg3r

## 🔗 Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1XsuWUulDDdktnV6fpPgRIH172iASvVmz/view)
- 🔍 **Prova:** [TryHackMe - 0ff3ns!v3 S3cur!ty - Sw4gg3r](https://tryhackme.com/room/0ff3nsv3s3curtysw4gg3r)

---

# depois de explorar como swagger....

![image](https://github.com/user-attachments/assets/f645cf56-c6ce-40f9-98a1-5fec134f9d25)

conteudo do .backup 
```txt
#!/bin/bash
##### Script em desenvolviment visualisar containers ######
###########################################################
######## verificando containers em execucao ###############
docker ps
a=$(docker ps | cut -d " " -f1 | grep -v "CONTAINER")

######################## Docker Inspect ###################
docker inspect $a
```

# escalando para root
![image](https://github.com/user-attachments/assets/bf139977-d1f1-4cc6-8afa-4439c19f50b9)

# bash -li (upgrade de shell)
![image](https://github.com/user-attachments/assets/56ab04c4-f382-4e91-a7e8-df4e53c5df1e)
agora é só ser feliz.

docker ps / docker inpect

![image](https://github.com/user-attachments/assets/79e11a7e-da0d-4f7b-83c3-8256d4c53299)

---
flag root 
---
![image](https://github.com/user-attachments/assets/e0610da5-e09a-459a-92a7-4b3ffba6163f)
---
![image](https://github.com/user-attachments/assets/edc189b9-5a6e-4a90-9abb-9e85ef9e8758)
---
![image](https://github.com/user-attachments/assets/9b1aa064-ce27-47f1-a1f4-7ce54265b4da)

