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
