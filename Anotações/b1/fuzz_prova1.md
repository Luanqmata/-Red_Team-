# Exploração da Máquina — 0ff3ns!v3 S3cur!ty - Sw4gg3r

## Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1XsuWUulDDdktnV6fpPgRIH172iASvVmz/view)
- 🔍 **Prova:** [TryHackMe - 0ff3ns!v3 S3cur!ty - Sw4gg3r](https://tryhackme.com/room/0ff3nsv3s3curtysw4gg3r)

---

![image](https://github.com/user-attachments/assets/5c2252f8-9c2d-436f-867e-3e97c8ebd7e5)
-----
![image](https://github.com/user-attachments/assets/00ec9858-12dd-45c2-88b2-5a86941257c5)
-----
![image](https://github.com/user-attachments/assets/145be49f-c64a-4ac9-8b22-a42d17fd7f71)
---- 
![image](https://github.com/user-attachments/assets/a3740925-1162-44ae-966a-1cb367c804f6)
----
![image](https://github.com/user-attachments/assets/d4cbd408-a1c8-4895-b84d-ced9aa3da559)
----
# Comando que usei para achar a flag: 
![image](https://github.com/user-attachments/assets/e818b708-9326-4833-a362-35cf34412b93)
( obs : como eu sabia que estava procurando uma flag coloquei /flag no final de temp/empresa/ , e por sorte encontrei )
---
![image](https://github.com/user-attachments/assets/591bacc9-22ca-49ff-aff3-92635004abb1)
----
# ACHEI *****
----
![image](https://github.com/user-attachments/assets/072244d4-a25d-4080-b8f7-f0f120db4b9f)

----
# ( Descobrir diretorio com injeção de host php )
## fuzing nesse caminho : temp/portal/nslookup ;
----
Navengando no git achei um lista de fuzz php 
lista: https://github.com/tjomk/wfuzz/blob/master/wordlist/fuzzdb/discovery/PredictableRes/PHP.fuzz.txt
![image](https://github.com/user-attachments/assets/7dceaf8c-9c80-4340-b059-cf427e391c06)
# checkando a pagina:
![image](https://github.com/user-attachments/assets/c83db763-2faf-408e-b76c-0a993d21d46f)
# Reparei que clicando em enviar aparece um metodo ?host= ,essa falha tem em comum mostrar o asquivos depois que vc coloca ; no final por exemplo:
http://192.168.100.207/temp/portal/nslookup/__index.php?host=yahoo.com;ls%20/
![image](https://github.com/user-attachments/assets/307b892f-c475-4193-a10d-5e6a4f6538ae)


