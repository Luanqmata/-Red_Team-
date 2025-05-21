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
