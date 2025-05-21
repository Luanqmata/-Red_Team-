# 🛡️ Exploração da Máquina — 0ff3ns!v3 S3cur!ty - Sw4gg3r

## 🔗 Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1XsuWUulDDdktnV6fpPgRIH172iASvVmz/view)
- 🔍 **Prova:** [TryHackMe - 0ff3ns!v3 S3cur!ty - Sw4gg3r](https://tryhackme.com/room/0ff3nsv3s3curtysw4gg3r)

---

### 📸 Prints

![img1](https://github.com/user-attachments/assets/5c2252f8-9c2d-436f-867e-3e97c8ebd7e5)
![img2](https://github.com/user-attachments/assets/00ec9858-12dd-45c2-88b2-5a86941257c5)
![img3](https://github.com/user-attachments/assets/145be49f-c64a-4ac9-8b22-a42d17fd7f71)
![img4](https://github.com/user-attachments/assets/a3740925-1162-44ae-966a-1cb367c804f6)
![img5](https://github.com/user-attachments/assets/d4cbd408-a1c8-4895-b84d-ced9aa3da559)

---

## 🏁 Comando para encontrar a FLAG

```bash
# Obs: como eu sabia que estava procurando uma flag, coloquei /flag no final de temp/empresa/
```

![img_flag](https://github.com/user-attachments/assets/e818b708-9326-4833-a362-35cf34412b93)

### ✅ FLAG ENCONTRADA!

![img_flag_found](https://github.com/user-attachments/assets/591bacc9-22ca-49ff-aff3-92635004abb1)
![image](https://github.com/user-attachments/assets/072244d4-a25d-4080-b8f7-f0f120db4b9f)
---

## 🕵️‍♂️ Descoberta de Diretório via Injeção de Host PHP

### 🧪 Fuzzing no caminho:
```
temp/portal/nslookup
```

Navegando no GitHub, encontrei uma lista de fuzz para PHP:  
🔗 https://github.com/tjomk/wfuzz/blob/master/wordlist/fuzzdb/discovery/PredictableRes/PHP.fuzz.txt

![img_fuzz](https://github.com/user-attachments/assets/7dceaf8c-9c80-4340-b059-cf427e391c06)

### 🔎 Verificando a página:

![img_page_check](https://github.com/user-attachments/assets/240ae9b3-430c-4025-89dc-e3706873dfea)

Reparei que, ao clicar em "enviar", aparece um parâmetro `?host=`.  
Essa falha permite executar comandos após colocar `;` no final.  
Exemplo:

```bash
http://192.168.100.207/temp/portal/nslookup/__index.php?host=yahoo.com;ls%20/
```

![img_exploit](https://github.com/user-attachments/assets/08036e6d-a273-4445-a951-57cc98c2b16c)

---
