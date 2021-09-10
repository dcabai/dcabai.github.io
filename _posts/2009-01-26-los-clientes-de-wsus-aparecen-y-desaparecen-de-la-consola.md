---
layout: single
title:  "Los Clientes de WSUS Aparecen y Desaparecen de la Consola"
categories: microsoft 
tags: microsoft wsus legacy
date:   2009-01-26 05:50:23 -0400
classes: wide
---

Muchas veces tenemos un problema en los equipos clientes que empiezan a **aparecer y desaparecer** de la consola, o sino puede que nunca aparezcan en la consola de **WSUS**. Algunas veces se debe al servicio de Windows Update en la misma PC, pero otras veces puede deberse a que el cliente fue clonado. Cuando alguien clona un equipo y éste ya se había conectado al WSUS puede que mantenga el mismo ID en los equipos y esto genera una especie de conflicto lo que hace que el mismo no aparezca en la consola. Otro comportamiento es que a veces aparezca uno de los equipos y otro día otro y hace que el anterior desaparezca misteriosamente.  
  
Tal vez tengas este comportamiento pero no hayas clonado el equipo o no estes seguro, igualmente puedes probar si esto resuelve tu problema de conexión de los equipos a la consola de WSUS. Para estos casos cree un **script** que simplemente borra algunas entradas del registro que se van a regenerar cuando se vuelva a conectar con el servidor de WSUS. Si el ID está repetido le asignará uno nuevo y así no tendremos mas este problema.  
  
Si tu problema es general también se puede asignar este script a una política (GPO) de dominio y así te aseguras que le corra a todos los equipos. También podrías agregar un flag para que no corra mas de una vez sino estaría borrando las entradas en cada logon. El flag puede ser un archivo o una entrada, cualquier condición que haga que no corra dos veces.  
  
Para poder usar el script copiá y pegá el contenido que paso a continuación en un notepad, grabalo con extensión .cmd o .bat y luego lo ejecutas o lo asignas a una GPO. Luego de eliminar las entradas en el registro se reconecta con el servidor de WSUS y regenera la autorización con el mismo.

```batch
@echo off
REM WSUS: Script para Eliminar entradas en el Registro por Clonado de Equipos
net stop wuauserv
REG DELETE "HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate" /v AccountDomainSid /f
REG DELETE "HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate" /v PingID /f
REG DELETE "HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate" /v SusClientId /f
REG DELETE "HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate" /v SUSClientIDValidation /f
net start wuauserv
wuauclt /resetauthorization /detectnow
exit
```