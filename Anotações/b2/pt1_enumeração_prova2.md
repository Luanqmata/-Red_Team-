
# Exploração da Máquina — TryHackMe Smith Exploitation Basic

## Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1T6XcA_A--FMGiI9jP0G8Lij6B2kIaHFi/view?usp=classroom_web&authuser=0)
- 🔍 **Prova:** [TryHackMe - Smith Exploitation Basic](https://tryhackme.com/jr/5m1thexploitationbasic)

---

## 🕵️‍♂️ Descobrindo IP da Máquina

```bash
IP Encontrado: 192.168.100.190
```
![IP da Máquina](https://github.com/user-attachments/assets/3b632005-77c8-4a41-b4f8-e006c4fbcfd7)

---

## 🔍 Mapeando Portas com Nmap

```bash
db_nmap -p 0-10000 192.168.100.190 -Pn
```
![Resultado Nmap](https://github.com/user-attachments/assets/12b626fa-06d3-4c46-92a3-bfe23249ac35)

---

## 🎯 Varredura de Serviços

```bash
db_nmap -sV -p 21,80,3389,8080 192.168.100.190 -Pn
```
![Serviços Detectados](https://github.com/user-attachments/assets/cf9b9a65-b85e-47ba-8a9b-706234b47999)

---

## 🧠 Informações Coletadas com Metasploit

![Metasploit Info](https://github.com/user-attachments/assets/49401462-af44-4521-9144-e9519cf47ce6)

---

## 🌐 OSINT no Site

![OSINT Resultado](https://github.com/user-attachments/assets/ad557d0e-bf01-4ea4-8948-964146e20640)

---

## 📋 Coletando Palavras para Fuzzing

```bash
wget -r -l1 -H -nd -A.html http://192.168.100.190
cat *.html | grep -oP '\w+' | sort -u > palavras.txt
dirsearch -u http://192.168.100.190 -w palavras.txt
```
![Dirsearch Rodando](https://github.com/user-attachments/assets/3a5ed0ec-c3e1-455c-bcea-f328a2064768)

---

## 🔧 Verificando Tecnologias Usadas

![Tecnologias 1](https://github.com/user-attachments/assets/727d7dc7-e016-429c-9da9-d5adf84ffffc)
![Tecnologias 2](https://github.com/user-attachments/assets/83b6cd2c-2fcb-44b0-bf27-eb51b0b1a5d2)

---

## ⚡ Usando Redias Win para Obter Informações

![Redias Scan](https://github.com/user-attachments/assets/2298840f-0797-440d-a319-28bd69eba38c)

---

### Resultado:

```txt
Digite a URL do site (ex: https://exemplo.com): http://192.168.100.190

=== Iniciando todas as verificacoes para a URL: http://192.168.100.190 ===

1️⃣ Captura Headers do Servidor:
Microsoft-IIS/10.0

2️⃣ Métodos HTTP Permitidos:
OPTIONS, TRACE, GET, HEAD, POST

3️⃣ Links Encontrados:
https://www.youtube.com/watch?v=Y7f98aduVJ8  
https://bootstrapmade.com/  
https://themewagon.com  

4️⃣ Código-Fonte do HTML:
<title>Company - Mentoria RedTeam - RedScan Academy</title>

5️⃣ Tecnologia Detectada:
ASP.NET

6️⃣ Status HTTP:
200 OK

7️⃣ Título da Página:
Company - Mentoria RedTeam - RedScan Academy

8️⃣ Robots.txt:
404 - File or directory not found.

9️⃣ Sitemap.xml:
404 - File or directory not found.

=== Todas as verificacoes foram concluídas! ===
```
![Redias Info Final](https://github.com/user-attachments/assets/bc491d96-2634-4123-8ea3-f765a8626de6)

---

## 💡 Observação

Sabemos que o servidor roda **ASP.NET**, isso já dá uma pista:  
Provavelmente aceita **arquivos .aspx**.

---

## 💾 Banco de Dados Suspeito: `magnam.aspx`

![Banco Magnam](https://github.com/user-attachments/assets/1797792d-dba5-40f5-94bc-1320114fe322)

---

## 💡 Upload de Arquivos Possível!

A questão é simples:  
Depois de subir o arquivo, para acessar, basta:

```url
http://192.168.100.190/magnam/[nome_do_arquivo]
```

---

## 🎯 Agora é só subir o Shell! 

E começar a brincadeira!
