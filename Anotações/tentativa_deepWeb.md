# ----- kali linux -----

sudo apt install tor
sudo apt install proxychains

2° saber qual a porta e config 
tail /etc/proxychains.conf

outro arquivo de config
tail /etc/proxychains4.conf
  se estiver os dois iguais significa que esta correto! 

Iniciar o tor :
sudo service tor start

comando para confirmar ultilização do serviço :
sudo netstat -nltp

* mostra processos * porta 9050

# ---------- ir nas configs do firefox proxy --------------

colocar em manual proxy config 

Habilitar SOCKS V5

HABILITAR PROXY DNS WHEN USING SOCKS V5

![image](https://github.com/user-attachments/assets/d0f9c069-9710-4223-acef-29077fe12afb)

# -------- NAVEGAR NA WEB ULTILIZANDO DUCK DUCK GO -----------

QUE NAO VAI PEDIR AS VERIFICAÇÕES 
pesquisar whats my ip para conferir se realmente esta dando os pulos do tor 


pesquisar hiden wiki no duckduckgo e dai clicar no primeiro link vc vai ter acesso a links do onion

para encerrar usar o mesmo comando de inciar porem parando o serviço do tor
