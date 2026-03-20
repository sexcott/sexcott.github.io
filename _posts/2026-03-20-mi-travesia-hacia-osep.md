---
layout: post
title: "OSEP: mi experiencia, consejos y trucos"
date: 2026-03-20
tags: [certificaciones, aprendizaje, recursos]
excerpt: "Algunos consejos, trucos y vivencias que me sirvieron para aprobar."
---

Hola, mi nombre es Angel Figueroa Scott. Soy pentester enfocado en aplicaciones web y móviles. En diciembre de **2025** obtuve la certificación impartida por OffSec: **OSEP (OffSec Experienced Penetration Tester)**.

Escribo esta pequeña entrada para contarles mi **experiencia**, así como algunos **consejos** y **trucos** que me sirvieron para aprobar esta certificación.

![OSEP](/assets/img/OSEP-Credential.jpg)

## Mi experiencia

Para comenzar, quiero decir que esta certificación fue la primera que obtuve de OffSec. Cabe mencionar que, al momento de agendar el examen, cometí un pequeño error: en lugar de programarlo para las 5:00 de la tarde del viernes, lo agendé para las 5:00 de la madrugada.

Me di cuenta de esto gracias a que OffSec suele enviar un correo horas antes para recordarte que el examen está a punto de comenzar. Comento esto para que, si alguno de ustedes desea obtener una certificación de esta plataforma, lo tenga en cuenta y no cometa este pequeño error, ya que si no entras durante la primera hora con el proctor, el examen queda cancelado.

Aclarado lo anterior, ahora sí puedo empezar con mi experiencia.

La primera hora del examen fue un paseo por el parque. Recuerdo haber obtenido las primeras dos flags durante esa primera hora, y las siguientes dos alrededor de la tercera hora. Mantuve ese ritmo hasta llegar aproximadamente a 9 flags, quedándome a solo una de la calificación mínima aprobatoria durante las primeras 10 horas.

Cuando llegué a la flag número 9, llevaba aproximadamente 10 horas de examen, y fue ahí donde casi perdí la cordura y estuve a punto de tirar la toalla. Recuerdo que intenté cosas completamente absurdas en ese punto. Además, durante todo el examen restringí demasiado mis horas de sueño, cosa que no recomiendo para nada. Estuve atrapado en ese bucle de demencia durante cerca de 12 horas.

Ese bucle se rompió cuando, por un suceso que pareció magia, logré ver algo que a simple vista podría parecer obvio. Una vez que vi **eso** y retomé mis apuntes, supe qué hacer e inmediatamente pude obtener la dichosa flag aprobatoria.

Fue en ese punto cuando decidí tomarme las cosas con más calma. Descansé unas cuantas horas, tomé capturas para el reporte y dormí un poco para despejar la mente. Cerca de la hora 30 ya tenía la `secret.txt`. Cabe mencionar que yo pensaba que obtener esa flag sería algo descabellado; sin embargo, si haces los laboratorios a conciencia, te resultará mucho más fácil llegar a ella.

Recuerdo que no quise completar todas las flags. Por un lado, el sueño me estaba matando, y por otro, el tiempo se estaba terminando. Así que, cuando quedaban aproximadamente 4 horas, decidí dejarlo todo y comenzar a redactar el informe.

Aquí vale la pena mencionar algo: puedes agilizar bastante este proceso si, al mismo tiempo que realizas el examen, vas llenando un pequeño writeup en tu Obsidian.

Entregué el examen y llegó el momento más tormentoso: esperar. Esperé cerca de 5 días hábiles para recibir el dichoso mensaje de OffSec en el que te indican que has aprobado el examen.

Recibí el resultado y, casi de inmediato, compré el voucher para el OSWE, ya que uno de mis propósitos de este año es convertirme en **OSCE3**, es decir, obtener **OSWE, OSEP y OSED**.

## Consejos

El consejo más importante que puedo darles es este: hagan todos los `laboratorios`. Si bien el curso cuenta con laboratorios base, existen dos que son especialmente importantes para aprobar, ya que estos dos corresponden a exámenes retirados.

Además del material del curso, algunos módulos de HTB Academy me resultaron de gran utilidad. Por mencionar algunos: [Intro to C2 Operations with Sliver](https://academy.hackthebox.com/app/module/241), [Introduction to Windows Evasion Techniques](https://academy.hackthebox.com/app/module/254) y [Active Directory Enumeration & Attacks](https://academy.hackthebox.com/app/module/143).

Los módulos de HTB fueron imprescindibles, ya que mi experiencia en Active Directory era bastante limitada. Había tocado AD en alguna que otra máquina de Hack The Box cuando competía en las sessions, pero eso fue hace dos años y gran parte de esa retención ya se había perdido.

Otro consejo es que gestionen bien sus horas de descanso. Por muy obvio que parezca, cuando una persona mantiene una concentración extrema en una sola cosa, suelen pasar dos cosas: pierde la noción del tiempo y gasta demasiada energía. No dormir y pasar demasiado tiempo dándole sin parar puede provocar un agotamiento extremo, lo cual perjudica el pensamiento racional. Así que prioricen mucho sus horas de sueño. Recuerden: no es una carrera, es un maratón.

Por último, y no menos importante, usen el Discord de OffSec. De verdad, úsenlo. No saben la cantidad de veces que me atoré en los laboratorios y gente del canal de OffSec, así como sus mentores, me ayudaron a seguir avanzando. Son personas que, como tú, están realizando el curso de la certificación. Eso quiere decir que, si buscas en el historial, quizá alguien ya tuvo esa misma duda y puedas darte una idea de cómo llevarla a cabo.

## Trucos

Y llegamos a la parte con más candela del post: los trucos. Para este examen utilicé decenas de recursos y atajos que me ayudaron a salir de apuros. Los voy a categorizar en una lista y después los iré explicando punto por punto:

1. Repositorios de GitHub
2. HTB Path
3. Hoja de trucos
4. Warp Terminal

### Repositorios de GitHub

Durante todo mi camino hacia la OSEP, me apoyé en varios repositorios que resultan de gran utilidad a la hora de evadir antivirus, explotar AD CS y trabajar con Sliver.

El primero es [The-Viper-One/OSEP-Notes](https://github.com/The-Viper-One/OSEP-Notes/tree/main), que cuenta con diversas secciones donde explican cómo llevar a cabo ataques, evadir antivirus, usar macros, hacer pivoting, aplicar process hollowing, entre muchas otras cosas.

El siguiente repositorio es [Anon-Exploiter/sliver-cheatsheet](https://github.com/Anon-Exploiter/sliver-cheatsheet?tab=readme-ov-file#lateral-movement), que, a diferencia del módulo de HTB Academy, cubre escenarios que no vienen en su contenido. Incluye decenas de configuraciones y múltiples formas de enumerar, autenticarse, ejecutar en memoria, hacer pivoting, entre otras tareas.

Si no quieres enredarte con la explotación de MSSQL, [ScorpionesLabs/MSSqlPwner](https://github.com/ScorpionesLabs/MSSqlPwner) puede ser tu salvación. Esta herramienta automatiza gran parte de la explotación de MSSQL y permite trabajar con Linked Servers, Impersonation, NTLM relay, entre otras cosas.

Para todo el tema de reconocimiento, explotación y postexplotación usé [seriotonctf/cme-nxc-cheat-sheet](https://github.com/seriotonctf/cme-nxc-cheat-sheet), que cuenta con una lista de escenarios donde NetExec puede entrar en acción. Usé NetExec durante todo el examen, ya que es una herramienta bastante potente y cuenta con cientos de módulos que automatizan ciertas tareas.

### HTB Path

En particular, yo usé el path que tiene 0xdf en su [blog](https://0xdf.gitlab.io/cheatsheets/offsec#osep-pen-300). Tiene cerca de 29 máquinas enumeradas, y cada una cuenta con un writeup. Por cierto, de ahí se puede aprender bastante sobre metodología.

Considero que, si completas cada una de esas máquinas, llegas con una ventaja importante al examen, ya que algunas incluso me parecieron más difíciles que ciertos laboratorios del OSEP.

### Hoja de trucos

Considero que este punto es de los más cruciales. Saber organizar, crear y consultar tus notas es una habilidad que, como pentester, se tiene que desarrollar.

En primer lugar, porque la memoria es fugaz: lo que hoy tienes muy presente, mañana podría no estarlo tanto. Por otro lado, una persona que documenta bien sus procesos suele retener mejor la información. Además, tener buenas notas te ahorra muchísimo tiempo al momento de consultar ataques o técnicas que ya realizaste y que vuelves a necesitar en otro contexto.

Por último, está la parte de la búsqueda. Buscar también tiene que ser un proceso organizado. Por eso, considero ideal usar `#tags` en tus notas para poder filtrar contenido fácilmente y encontrar lo que necesitas sin perder tiempo.

### Warp Terminal

Aunque parezca chiste, Warp Terminal me fue de gran utilidad durante el examen. Como utilicé WSL con Kali, Warp fue mi terminal principal tanto en mis jornadas de estudio como durante el examen.

Este terminal tiene una sección muy útil que te permite crear tus propios templates de comandos. Dichos templates pueden incluir variables y descripciones, lo cual resulta bastante práctico cuando trabajas con comandos largos o repetitivos.

A continuación, muestro un ejemplo de cómo organizo mis templates:

![Ejemplo de templates en Warp Terminal](/assets/img/image.png)

Para crear un template, basta con presionar `+ -> $_Workflow`. Esto abre una ventana para crear uno nuevo. El siguiente ejemplo corresponde a un template que tengo para BloodyAD y que utilizo para aprovechar el privilegio `ReadLAPSPassword`.

![Template de BloodyAD en Warp Terminal](/assets/img/workSpace.png)

Para usarlo, basta con invocarlo desde el Workspace. Una vez abierto, se verá así, permitiéndote ir iterando con la tecla Tab para rellenar las variables asignadas:

![Uso de variables en un template de Warp Terminal](/assets/img/variables.png)

## Cierre

Si bien la certificación es demandante, considero que está lejos de ser imposible. Yo llegué al curso sin saber casi nada de Active Directory; lo fui aprendiendo al mismo tiempo que la evasión y, aun así, logré aprobar al primer intento.

Mi recomendación es que estudies con intención: no te satures, pero tampoco te confíes. Vale más una hora bien aprovechada que ocho horas frente a la pantalla sin retener realmente nada.

Para cerrar, solo me queda agradecer a OffSec por ofrecer un curso tan completo, capaz de sentar bases muy sólidas en el mundo de la evasión.

---


