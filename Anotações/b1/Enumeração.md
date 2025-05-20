# Exploração da Máquina — 0ff3ns!v3 S3cur!ty - Sw4gg3r

## Links

- 💻 **Máquina:** [Google Drive - Máquina](https://drive.google.com/file/d/1XsuWUulDDdktnV6fpPgRIH172iASvVmz/view)
- 🔍 **Prova:** [TryHackMe - 0ff3ns!v3 S3cur!ty - Sw4gg3r](https://tryhackme.com/room/0ff3nsv3s3curtysw4gg3r)

---
# Ip alvo : 192.168.100.207

![image](https://github.com/user-attachments/assets/d1c3b4f5-6e16-44c0-bd8e-fafa0461e7bf)

(Enumeração superficial)

---
## com scanner/ssh/ssh_version
```txt
=================================

  Type                     Value                                 Note
  ----                     -----                                 ----
  encryption.compression   none
  encryption.compression   zlib@openssh.com
  encryption.encryption    aes128-ctr
  encryption.encryption    aes192-ctr
  encryption.encryption    aes256-ctr
  encryption.encryption    arcfour256                            Deprecated
  encryption.encryption    arcfour128                            Deprecated
  encryption.encryption    aes128-gcm@openssh.com
  encryption.encryption    aes256-gcm@openssh.com
  encryption.encryption    chacha20-poly1305@openssh.com
  encryption.encryption    aes128-cbc                            Deprecated
  encryption.encryption    3des-cbc                              Deprecated
  encryption.encryption    blowfish-cbc                          Deprecated
  encryption.encryption    cast128-cbc                           Deprecated
  encryption.encryption    aes192-cbc                            Deprecated
  encryption.encryption    aes256-cbc                            Deprecated
  encryption.encryption    arcfour                               Deprecated
  encryption.encryption    rijndael-cbc@lysator.liu.se           Deprecated
  encryption.hmac          hmac-md5-etm@openssh.com
  encryption.hmac          hmac-sha1-etm@openssh.com
  encryption.hmac          umac-64-etm@openssh.com
  encryption.hmac          umac-128-etm@openssh.com
  encryption.hmac          hmac-sha2-256-etm@openssh.com
  encryption.hmac          hmac-sha2-512-etm@openssh.com
  encryption.hmac          hmac-ripemd160-etm@openssh.com
  encryption.hmac          hmac-sha1-96-etm@openssh.com
  encryption.hmac          hmac-md5-96-etm@openssh.com
  encryption.hmac          hmac-md5                              Deprecated
  encryption.hmac          hmac-sha1
  encryption.hmac          umac-64@openssh.com
  encryption.hmac          umac-128@openssh.com
  encryption.hmac          hmac-sha2-256
  encryption.hmac          hmac-sha2-512
  encryption.hmac          hmac-ripemd160                        Deprecated
  encryption.hmac          hmac-ripemd160@openssh.com
  encryption.hmac          hmac-sha1-96                          Deprecated
  encryption.hmac          hmac-md5-96                           Deprecated
  encryption.host_key      ssh-rsa
  encryption.host_key      ssh-dss
  encryption.host_key      ecdsa-sha2-nistp256                   Weak elliptic curve
  encryption.host_key      ssh-ed25519
  encryption.key_exchange  curve25519-sha256@libssh.org
  encryption.key_exchange  ecdh-sha2-nistp256
  encryption.key_exchange  ecdh-sha2-nistp384
  encryption.key_exchange  ecdh-sha2-nistp521
  encryption.key_exchange  diffie-hellman-group-exchange-sha256
  encryption.key_exchange  diffie-hellman-group-exchange-sha1    Deprecated
  encryption.key_exchange  diffie-hellman-group14-sha1
  encryption.key_exchange  diffie-hellman-group1-sha1            Deprecated
  fingerprint_db           ssh.banner
  openssh.comment          Ubuntu-2ubuntu2.13
  os.cpe23                 cpe:/o:canonical:ubuntu_linux:14.04
  os.family                Linux
  os.product               Linux
  os.vendor                Ubuntu
  os.version               14.04
  service.cpe23            cpe:/a:openbsd:openssh:6.6.1p1
  service.family           OpenSSH
  service.product          OpenSSH
  service.protocol         ssh
  service.vendor           OpenBSD
  service.version          6.6.1p1
```
Enumerando Porta ftp protocolos http
![image](https://github.com/user-attachments/assets/ef712d78-f460-4553-9823-f86f7837372c)

![image](https://github.com/user-attachments/assets/cb219bd7-fe23-45e2-b15a-64fda2131c26)

![image](https://github.com/user-attachments/assets/6d019be9-777b-4e4a-9918-c21b61f709e5)
