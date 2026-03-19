---
title: "Mi experiencia preparando el OSCP: lo que nadie te dice"
excerpt: "Un recorrido honesto por el proceso de estudio, los recursos que usé y los errores que cometí en el camino."
category: Certificaciones
---

Llevar meses preparándote para un examen de 24 horas tiene algo de absurdo y algo de adictivo. Aquí te cuento cómo está yendo mi proceso.

## Por qué el OSCP

Después de varios meses en TryHackMe y HackTheBox, sentí que necesitaba una meta concreta. El OSCP tiene la reputación de ser *el* examen que te obliga a pensar por ti mismo, sin muletas.

## Lo que más me está costando

El **Buffer Overflow** en x86 fue mi primer gran muro. Pasar de entender el concepto a ejecutarlo sin guía en un examen es otra historia.

```python
# Esqueleto básico para fuzzing
import socket, sys

ip   = "192.168.x.x"
port = 1337
buf  = b"A" * 100

while True:
    try:
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect((ip, port))
        s.send(buf)
        s.close()
        buf += b"A" * 100
    except:
        print(f"Crash con {len(buf)} bytes")
        sys.exit()
```

## Recursos que recomiendo

1. **TCM Security — Practical Ethical Hacking**: el mejor curso de preparación en precio/calidad.
2. **TryHackMe Buffer Overflow Prep**: room perfecta para practicar el proceso completo.
3. **HTB máquinas retiradas**: empieza por las Easy de Linux antes de pasar a Windows y Active Directory.

---

Si estás en el mismo camino, no dudes en contactarme. La comunidad lo es todo.
