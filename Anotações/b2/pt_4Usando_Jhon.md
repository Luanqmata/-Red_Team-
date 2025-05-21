# Exploração da Máquina — TryHackMe Smith Exploitation Basic

## Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1T6XcA_A--FMGiI9jP0G8Lij6B2kIaHFi/view?usp=classroom_web&authuser=0)
- 🔍 **Prova:** [TryHackMe - Smith Exploitation Basic](https://tryhackme.com/jr/5m1thexploitationbasic)

---
# Guia de Transferência e Quebra de Hash - Capture The Flag

## 1️⃣ Transferindo o Arquivo Sensível

Após localizar o arquivo sensível, precisamos transferi-lo usando a aba de gerenciamento do **Magnam**, onde é possível **upar**, **deletar** e **baixar** arquivos. O objetivo é enviar o arquivo para esta aba e, em seguida, fazer o download.

![Transferindo Arquivo](https://github.com/user-attachments/assets/520f0fd1-f10e-4ba7-aa28-9a699cc0cb7a)

---

## 2️⃣ Identificando o Local do Arquivo

Localize corretamente o caminho do arquivo sensível que será transferido.

![Identificando Local](https://github.com/user-attachments/assets/a55b764b-3dec-4331-b116-7fbb1f6b6153)

---

## 3️⃣ Copiando o Arquivo para Transferência

Agora basta usar o comando `copy` para mover o `arquivosensivel.zip` até o diretório acessível via Magnam e baixar no Kali para quebrar o hash com o **John The Ripper**.

![Copiando Arquivo](https://github.com/user-attachments/assets/2b108c2a-badc-4f05-8f6f-228442189844)

---

## 4️⃣ Arquivo Copiado com Sucesso!

Depois da cópia, volte para o Kali Linux e baixe o arquivo `.zip`.

![Arquivo Copiado](https://github.com/user-attachments/assets/2759e50d-7787-47b5-bcca-66bbb3561897)

---

## 5️⃣ Download no Kali

No Kali, faça o download do arquivo `.zip`.

![Download do Zip](https://github.com/user-attachments/assets/a0ee3115-c85f-4378-acb2-c8e8937e19ae)

---

## 6️⃣ Extraindo o Arquivo `.zip`

Ao tentar extrair, será solicitada uma senha. Como se trata de um arquivo `.zip`, vamos utilizar o `zip2john` para extrair o hash.

![Extraindo o Zip](https://github.com/user-attachments/assets/51bd43c9-00af-4b8a-983b-ed98d8ce6333)

---

## 7️⃣ Obtendo o Hash com `zip2john`

Extraia o hash do arquivo `.zip` com o `zip2john`.

![Obtendo o Hash](https://github.com/user-attachments/assets/eb5c4335-58ef-4d10-9f7b-73ee8f12f83e)

---

## 8️⃣ Quebrando o Hash com RockYou

Utilize a famosa wordlist **rockyou.txt** para quebrar o hash.

Senha encontrada: `panther`

![Quebrando Hash 1](https://github.com/user-attachments/assets/13075f33-b8de-4550-9cde-f9b75c461cc7)  
![Quebrando Hash 2](https://github.com/user-attachments/assets/dc30d3dc-3048-436a-b4d7-306dcb0f8b8f)  
![Quebrando Hash 3](https://github.com/user-attachments/assets/8bb3b6df-6422-440e-8e84-66d51f8c211d)  
![Quebrando Hash 4](https://github.com/user-attachments/assets/d92c0694-edd2-46d7-80ae-cdbcb571ebb8)

---

## 9️⃣ Descobrindo a Página de Login

Conforme as informações, existe uma página de login rodando na **porta 8080**.

Acesse: `http://IP:8080`

![Página de Login](https://github.com/user-attachments/assets/a1732f7c-f358-4172-ba81-98ff8e23f0cb)

### 🔍 Dica:
Para descobrir a versão do Jenkins: `http://IP:8080/oops`

---

## 🔧 Acessando o Jenkins Script Console

Após acessar o Jenkins, navegue até **Gerenciamento > Scripting** para abrir o terminal Groovy.

![Jenkins Console](https://github.com/user-attachments/assets/98061983-d5fe-4c46-9e7a-255aefdd5ad7)

---

## 🔊 Preparando o Netcat

Inicie o **Netcat** para escutar a porta `4444` (ou qualquer outra de sua escolha).

![Netcat](https://github.com/user-attachments/assets/ee3861f4-908f-437e-a086-960eb88dddf7)

---

## 💻 Gerando Shell Groovy

Utilize um **gerador de shell** e selecione:  
- **Groovy**  
- Comando: `cmd` (Windows)

![Gerador de Shell](https://github.com/user-attachments/assets/86baebd5-ca76-414f-a2b9-9107c28733bd)

---

## 💥 Executando o Payload

Cole o código no console Groovy e execute.

![Executando Payload](https://github.com/user-attachments/assets/7ed2288a-4d89-428f-9ddc-bb7d4617ef49)

---

## 📡 Escutando com Netcat

Após execução, o Netcat que estava escutando capturará a conexão reversa.

![Conexão Capturada](https://github.com/user-attachments/assets/83769602-6357-413a-a1f3-813bdae33f61)

---

## 🏴‍☠️ Acesso como SYSTEM

Agora com autoridade **SYSTEM**, é possível explorar qualquer pasta ou recurso da máquina!

![Acesso SYSTEM 1](https://github.com/user-attachments/assets/c1e967bd-f8a5-418b-b13a-673c70002896)  
![Acesso SYSTEM 2](https://github.com/user-attachments/assets/4ae46ce3-0699-48fe-bf73-89775f233e52)

---

## 💡 Conclusão

Esse é um exemplo clássico de exploração que envolve transferência de arquivos sensíveis, quebra de hash e escalonamento de privilégios via Jenkins.  
⚠️ **Importante:** sempre pratique essas técnicas em ambientes controlados e autorizados!

