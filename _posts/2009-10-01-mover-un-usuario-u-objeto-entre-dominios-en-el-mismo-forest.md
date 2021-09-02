---
layout: single
title:  "Mover un Usuario u Objeto entre Dominios en el mismo Forest"
categories: microsoft
tags: microsoft activedirectory
date:   2009-11-18 05:50:23 -0400
classes: wide
---

El otro día me encontré con un requerimiento que era mover un usuario entre dominios de un mismo forest nativo. Obviamente no se puede hacer Drag & Drop y desde la GUI tampoco funciona aunque te pares en el RID master del dominio destino.  
  
Entonces busqué la opción por comandos porque la tarea en si, se puede realizar. Al hacer esto me topé con un comando que no había utilizado nunca y me pareció que vale la pena comentar, **MoveTree**.  
  
Este comando me pareció muy útil y viene cuando se instalan las Support Tools de Windows Server 2003. Te permite mover cualquier objeto entre dominios del mismo forest siempre y cuando esté todo en modo nativo.  
  
El comando trabaja de la siguiente manera, cuando se mueve un objeto primero se pone en el contenedor **Lost & Found** del dominio origen y luego si todo está bien en cuanto a los requisitos es movido al dominio destino. Si se encuentra un error lo deja ahí. Ahora bien antes podemos ejecutar un modo de chequeo que nos alerta ante cualquier posible problema, lo cual es extremadamente útil.  
  
El comando tiene los siguientes modificadores u opciones:
```batch
THE SYNTAX OF THIS COMMAND IS:

MoveTree [/start | /continue | /check] [/s SrcDSA] [/d DstDSA]
         [/sdn SrcDN] [/ddn DstDN] [/u Domain\\Username] [/p Password] [/verbose]

  /start        : Start a move tree operation with /check option by default.
                : Instead, you could be able to use /startnocheck to start
                : a movtree operation without any check.
  /continue     : Continue a failed move tree operation.
  /check        : Check the whole tree before actually move any object.
  /s <SrcDSA>   : Source server\'s fully qualified primary DNS name. Required
  /d <DstDSA>   : Destination server\'s fully qualified primary DNS name.
                : Required
  /sdn <SrcDN>  : Source sub-tree\'s root DN.
                : Required in Start and Check case. Optional in Continue case
  /ddn <DstDN>  : Destination sub-tree\'s root DN. RDN plus Destinaton Parent DN.
                : Required

  /u <Domain\\UserName>  : Domain Name and User Account Name. Optional
  /p <Password> : Password. Optional
  /verbose      : Verbose Mode. Pipe anything onto screen. Optional
```

Algunos puntos que debemos tener en cuenta en el movimiento de los objetos es que se resuelvan correctamente los nombres de los servidores, que se tengan los permisos necesarios para la operación, y pararse en el domain controller con el rol de RID master.

También podemos usar este comando para mover cuentas de máquina pero como dice la documentación, una vez movida la máquina no se va a poder loguear al nuevo dominio, para eso habría que utilizar el comando anterior y conocido **netdom**. 

Un ejemplo para mover un usuario sería el siguiente:
```batch
movetree /start /s servidor_origen.dominio1.com /d servidor_destino.dominio2.com /sdn "CN=Diego Cabai,OU=Usuarios,OU=Empresa,DC=dominio1,DC=com" /ddn "CN=Diego Cabai,CN=Users,DC=dominio2,DC=com" /verbose
```
Como se ve en el comando también podemos cambiar la OU donde va a parar el usuario ya que tal vez no tengamos creada la misma estructura pero si debemos especificarla. Lo mismo con el nombre completo del usuario también debe figurar.

Por último si queremos saber si este comando correría correctamente debemos cambiar el **/start** por un **/check** y ahí nos dirá si el movimiento será exitoso. Por último si el usuario tenía una cuenta de correo en Exchange luego de que la replicación se realice entre los domain controllers podrán ejecutar el Move Mailbox común y corriente para depositar la casilla en un servidor de Exchange del nuevo dominio.

Link | [Movetree.exe Technet Archive](http://technet.microsoft.com/en-us/library/cc755718%28WS.10%29.aspx)