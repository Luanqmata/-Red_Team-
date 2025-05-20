
# Aprofundamento de Scan no Metasploit

Este repositório contém informações sobre como realizar scans aprofundados tanto em sistemas Windows quanto Linux, utilizando o Metasploit Framework (MSF6). Abaixo estão descritos os módulos utilizados para explorar e realizar scans nos dois sistemas operacionais.

## Scans em Windows

### 1. **Scanner SMB (Serviços SMB no Windows)**
- **`scanner/smb/smb_version`**: Identifica a versão do protocolo SMB.
- **`scanner/smb/smb_enumshares`**: Enumera os compartilhamentos de arquivos no sistema.
- **`scanner/smb/smb_enumusers`**: Enumera os usuários válidos do SMB.

### 2. **Scanner RDP (Remote Desktop Protocol - RDP)**
- **`scanner/rdp/rdp_scanner`**: Realiza um scan para verificar se a porta RDP (3389) está aberta e identifica os sistemas com o serviço RDP ativo.

### 3. **SSH (Secure Shell) no Windows**
- **`scanner/ssh/ssh_version`**: Identifica a versão do servidor SSH.
- **`scanner/ssh/ssh_login`**: Realiza brute force em usuários e senhas do SSH.

## Scans em Linux

### 1. **Scanner SMB (Samba no Linux)**
- **`scanner/smb/smb_version`**: Identifica a versão do protocolo SMB no Linux (geralmente com o Samba).
- **`scanner/smb/smb_enumshares`**: Enumera os compartilhamentos de arquivos via Samba.
- **`scanner/smb/smb_enumusers`**: Enumera os usuários válidos do Samba.

### 2. **Scanner SSH (SSH no Linux)**
- **`scanner/ssh/ssh_version`**: Identifica a versão do servidor SSH.
- **`scanner/ssh/ssh_login`**: Brute force de usuários e senhas para o SSH.
- **`auxiliary/scanner/ssh/ssh_enumusers`**: Enumera usuários SSH válidos utilizando técnicas baseadas em tempo de resposta.

### 3. **Scanner HTTP (Apache/Nginx no Linux)**
- **`scanner/http/http_version`**: Identifica a versão do servidor HTTP (Apache, Nginx, etc).
- **`scanner/http/http_methods`**: Verifica os métodos HTTP habilitados (GET, POST, PUT, etc).
- **`scanner/http/dir_scanner`**: Tenta explorar caminhos comuns de diretórios em servidores HTTP.
- **`scanner/http/apache_userdir_enum`**: Tenta descobrir diretórios de usuários no Apache.

### 4. **Scanner MySQL (Banco de Dados no Linux)**
- **`scanner/mysql/mysql_login`**: Realiza brute force em credenciais de login MySQL.
- **`scanner/mysql/mysql_schemadump`**: Realiza dump da estrutura de esquemas do MySQL.

### 5. **Scanner FTP (Serviços FTP no Linux)**
- **`scanner/ftp/ftp_version`**: Identifica a versão do servidor FTP.
- **`scanner/ftp/ftp_login`**: Realiza brute force ou tenta login anônimo.
- **`scanner/ftp/anonymous`**: Verifica se o login anônimo está habilitado no servidor FTP.

### 6. **Scanner NFS (Network File System no Linux)**
- **`scanner/nfs/nfs_mount`**: Descobre exportações NFS acessíveis.
- **`scanner/nfs/nfsmount`**: Tenta montar diretórios NFS remotos.

## Conclusão
Os módulos listados acima são apenas uma parte das ferramentas poderosas do Metasploit para explorar e realizar reconhecimento profundo em sistemas Windows e Linux. A combinação destes módulos com payloads avançados do MSF6 pode resultar em explorações eficazes, dependendo da configuração e dos serviços ativos em cada máquina.

---

## Payloads do MSF6

Existem vários payloads disponíveis no Metasploit Framework, entre os quais:
- **`meterpreter/reverse_tcp`**: Payload reverso TCP, frequentemente utilizado para obter uma shell interativa.
- **`cmd/unix/reverse_python`**: Payload reverso para sistemas Unix utilizando Python.


```txt

Aprofundamento de Scan em Windows e Linux com Payloads do MSF6:

Windows:

- scanner/smb/smb_version
- scanner/smb/smb_enumshares
- scanner/smb/smb_enumusers
- scanner/rdp/rdp_scanner
- scanner/ssh/ssh_version
- scanner/ssh/ssh_login

Linux:

- scanner/smb/smb_version
- scanner/smb/smb_enumshares
- scanner/smb/smb_enumusers
- scanner/ssh/ssh_version
- scanner/ssh/ssh_login
- auxiliary/scanner/ssh/ssh_enumusers
- scanner/http/http_version
- scanner/http/http_methods
- scanner/http/dir_scanner
- scanner/http/apache_userdir_enum
- scanner/mysql/mysql_login
- scanner/mysql/mysql_schemadump
- scanner/ftp/ftp_version
- scanner/ftp/ftp_login
- scanner/ftp/anonymous
- scanner/nfs/nfs_mount
- scanner/nfs/nfsmount

Payloads do MSF6:
- meterpreter/reverse_tcp
- cmd/unix/reverse_python

```

Ping para descobrir todos os endereços que estao na sua rede , descubra seu ip ultimos ultimos 3 numeros coloque 0/24 , fazer o scan na rede
 nmap -sn 192.168.100.0/24
