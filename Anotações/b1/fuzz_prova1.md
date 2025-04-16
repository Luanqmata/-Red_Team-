![image](https://github.com/user-attachments/assets/5c2252f8-9c2d-436f-867e-3e97c8ebd7e5)
-----
![image](https://github.com/user-attachments/assets/00ec9858-12dd-45c2-88b2-5a86941257c5)
-----
![image](https://github.com/user-attachments/assets/139f87d6-a78c-44ad-b262-e0826277a55d)
----
![image](https://github.com/user-attachments/assets/a3740925-1162-44ae-966a-1cb367c804f6)
----
![image](https://github.com/user-attachments/assets/d4cbd408-a1c8-4895-b84d-ced9aa3da559)
----
![image](https://github.com/user-attachments/assets/591bacc9-22ca-49ff-aff3-92635004abb1)
----
# ACHEI *****
----
![image](https://github.com/user-attachments/assets/072244d4-a25d-4080-b8f7-f0f120db4b9f)
----
# Comando que usei para achar a flag: 
![image](https://github.com/user-attachments/assets/e818b708-9326-4833-a362-35cf34412b93)
( obs : como eu sabia que estava procurando uma flag coloquei /flag no final de temp/empresa/ , e por sorte encontrei )
----
![image](https://github.com/user-attachments/assets/75263af5-e1fe-43d5-be37-d0c1a566ef4f)
# ( Descobrir diretorio com injeção de host php )
## fuzing nesses 3 caminhos : temp/portal ; temp/images ; temp/assets ;
```.txt
-- lista comum -- 
ffuf -u http://10.10.199.189/temp/portal/FUZZ -w /usr/share/seclists/Discovery/Web-Content/common.txt -e .html,.php,.jpg,.js,.css
ffuf -u http://10.10.199.189/temp/images/FUZZ -w /usr/share/seclists/Discovery/Web-Content/common.txt -e .html,.php,.jpg,.js,.css
ffuf -u http://10.10.199.189/temp/assets/FUZZ -w /usr/share/seclists/Discovery/Web-Content/common.txt -e .html,.php,.jpg,.js,.css

-- listas cabulosas --
ffuf -u http://10.10.199.189/temp/portal/FUZZ -w /usr/share/seclists/Discovery/Web-Content/raft-large-directories.txt -e .html,.php,.jpg,.js,.css
ffuf -u http://10.10.199.189/temp/images/FUZZ -w /usr/share/seclists/Discovery/Web-Content/raft-large-files.txt -e .html,.php,.jpg,.js,.css
ffuf -u http://10.10.199.189/temp/assets/FUZZ -w /usr/share/seclists/Discovery/Web-Content/raft-large-files.txt -e .html,.php,.jpg,.js,.css

-- Comandos com dirsearch --
dirsearch -u http://10.10.199.189/temp/portal -w /usr/share/wordlists/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt -r -e php -t 50
dirsearch -u http://10.10.199.189/temp/images -w /usr/share/wordlists/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt -r -e php -t 50
sudo dirsearch -u http://10.10.199.189/temp/assets -w /usr/share/wordlists/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt -r -e php -t 50


 ```
----
![image](https://github.com/user-attachments/assets/145be49f-c64a-4ac9-8b22-a42d17fd7f71)
### dirsearch -u http://10.10.199.189/temp/portal/nslookup/ -w /usr/share/wordlists/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt -r -e php -t 50
### dirsearch -u http://10.10.199.189/temp/portal/nslookup/ -w /usr/share/wordlists/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt -r -e php,txt,log,js,css,xml,htm,jpg,png,csv,asp,jar,sql,bak,svg -t 50
![image](https://github.com/user-attachments/assets/2c82237e-b31d-40b6-8702-99df08c9c50b)
----
![image](https://github.com/user-attachments/assets/fef3957b-bd78-4e8f-8383-2d97e6e1e67d)

