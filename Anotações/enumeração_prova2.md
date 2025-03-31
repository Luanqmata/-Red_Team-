# Desconbrindo IP da Maq
## 192.168.100.190

![image](https://github.com/user-attachments/assets/3b632005-77c8-4a41-b4f8-e006c4fbcfd7)

# db_nmap -p 0-10000 192.168.100.190 -Pn

![image](https://github.com/user-attachments/assets/12b626fa-06d3-4c46-92a3-bfe23249ac35)

# db_nmap -sV -p 21,80,3389,8080 192.168.100.190 -Pn
![image](https://github.com/user-attachments/assets/cf9b9a65-b85e-47ba-8a9b-706234b47999)

# msf_6 (Info_levantadas)

![image](https://github.com/user-attachments/assets/49401462-af44-4521-9144-e9519cf47ce6)

# osintando o site 
![image](https://github.com/user-attachments/assets/ad557d0e-bf01-4ea4-8948-964146e20640)



# Pegando todas palavras do site para usar no dirsearch
wget -r -l1 -H -nd -A.html http://192.168.100.190
cat *.html | grep -oP '\w+' | sort -u > palavras.txt
dirsearch -u http://192.168.100.190 -w palavras.txt

![image](https://github.com/user-attachments/assets/3a5ed0ec-c3e1-455c-bcea-f328a2064768)

## verificando tecnologias do site 
![image](https://github.com/user-attachments/assets/727d7dc7-e016-429c-9da9-d5adf84ffffc)
![image](https://github.com/user-attachments/assets/83b6cd2c-2fcb-44b0-bf27-eb51b0b1a5d2)

# Usando meu programa Redias win para obter informaçoes do site 

![image](https://github.com/user-attachments/assets/2298840f-0797-440d-a319-28bd69eba38c)

```txt

Digite a URL do site (ex: https://exemplo.com): http://192.168.100.190

=== Iniciando todas as verificacoes para a URL: http://192.168.100.190 ===
                                                                                                                                                                                                                                                                                                                                                                                                                                                                    === 1. Captura Headers do Servidor ===                                                                                                                                                                                                                                                                                                                                                                                                                               Escaneando Headers...

 O servidor roda:
Microsoft-IIS/10.0                                                                                                                                                                                                                                                                                                                                                                                                                                                  === 2. Descobre os Metodos HTTP Permitidos ===                                                                                                                                                                                                                                                                                                                                                                                                                       Verificando metodos HTTP suportados...

 Metodos permitidos pelo servidor:
OPTIONS, TRACE, GET, HEAD, POST

=== 3. Lista os Links Encontrados no HTML ===

 Procurando links na pagina...

 Links encontrados:

https://www.youtube.com/watch?v=Y7f98aduVJ8
https://bootstrapmade.com/
âhttps://themewagon.com

=== 4. Obtem Codigo-Fonte do HTML ===

 Obtendo codigo-fonte do HTML...

 Codigo HTML recebido:
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <meta content="width=device-width, initial-scale=1.0" name="viewport">
  <title>Company - Mentoria RedTeam - RedScan Academy</title>
  <meta name="description" content="">
  <meta name="keywords" content="">

  <!-- Favicons -->
  <link href="assets/img/favicon.png" rel="icon">
  <link href="assets/img/apple-touch-icon.png" rel="apple-touch-icon">

  <!-- Fonts -->
  <link href="https://fonts.googleapis.com" rel="preconnect">


=== 5. Detecta Tecnologias Utilizadas ===

 Detectando tecnologias utilizadas...

 Tecnologia detectada:
ASP.NET

=== 6. Obtem Codigo de Status HTTP ===

 Obtendo codigo de status HTTP...

 Status Code:
200

=== 7. Obtem o <title> da Pagina ===

 Obtendo titulo da pagina...

 Titulo da pagina:
Company - Mentoria RedTeam - RedScan Academy

=== 8. Verifica o arquivo robots.txt ===

 Procurando robots.txt...

Erro ao buscar robots.txt: Server Error
404 - File or directory not found.
The resource you are looking for might have been removed, had its name changed, or is temporarily unavailable.

=== 9. Verifica se o site possui um Sitemap ===

 Verificando sitemap.xml...

Erro ao buscar sitemap.xml: Server Error
404 - File or directory not found.
The resource you are looking for might have been removed, had its name changed, or is temporarily unavailable.

=== Todas as verificacoes foram concluiÂ­das! ===


Pressione Enter para continuar...
```
![image](https://github.com/user-attachments/assets/bc491d96-2634-4123-8ea3-f765a8626de6)
## Obtive ainformação que tem um ASPnet rodando e de acordo com a analise magnam com asp net pode ter arquivo .aspx 

