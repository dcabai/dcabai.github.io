---
layout: single
title:  "Listar los Distribution Groups Filtrando por AcceptMessagesOnlyFrom"
categories: exchange powershell microsoft
tags: exchange powershell microsoft
date:   2009-11-18 05:50:23 -0400
classes: wide
---
A veces surgen tareas cotidianas que uno requiere hacer y lo lleva a investigar la mejor forma de hacerlo. En este caso necesitábamos una lista de todas las listas de distribución o Distribution Groups de un ambiente con Exchange 2007 que tengan configurada la aceptación de correo de sólo ciertos usuarios y además que me liste esos usuarios por cada DL.  
  
Para esto como estamos usando Exchange 2007 creo que lo mejor era usar PowerShell, de esta manera podemos unificar todo en un comando y hacer un export del resultado de los grupos que estan restringidos y a su vez el listado de los usuarios que tienen acceso a enviarle correo.  
  
Si no estas al tanto de PowerShell o cómo se usa podes revisar este sitio que hay otros artículos donde explico un poco mejor ese punto. En esta ocasión voy a asumir que existe algo de conocimiento y el comando a ejecutar sería el siguiente:

```powershell
Get-DistributionGroup -ResultSize Unlimited -filter {AcceptMessagesOnlyFrom –ne $null} | select-object Name,@{Name="AcceptMessagesOnlyFrom";Expression={[string]::join(";",$_.AcceptMessagesOnlyFrom)}} | export-csv c:\\acceptmessages.csv
```

El comando a usar es **Get-DistributionGroup** que si en vez de las DL comunes debemos obtener las dinámicas entonces tendríamos que cambiarlo por **Get-DynamicDistributionGroup**. Luego con el **–ResultSize Unlimited** hacemos que pueda obtener todos los datos y no que esté limitado como si lo está por defecto. Hasta ahora nos va a listar todas las DL, por eso usamos el **–filter** junto con el parámetro **AcceptMessageOnlyFrom**, gracias a eso filtramos las DL que estan restringidas y por último lo exportamos en CSV con el **export-csv**. Importante, el comando debe quedar todo en una sola línea, es probable que se copie con saltos, pero arreglenlo para que quede en una sola.

El resultado que obtenemos es algo así:

> #TYPE System.Management.Automation.PSCustomObject  
> Name,AcceptMessagesOnlyFrom  
> “ListaUno”,"dominio.com/OU/usuario1;dominio.com/OU/usuario2;dominio.com/OU/usuario3”  
> "ListaDos","dominio.com/OU/usuario4”  
> "ListaTres","dominio.com/OU/usuario4;dominio.com/OU/usuario1”

Como ven es muy intuitivo de identificar el Grupo o Lista y luego los usuarios que si tienen permiso para enviar correo a dicha Lista. Espero que les sirva y les haga un poco mas sencilla la vida de administrar Exchange 2007. Dejo algunos links interesantes de Technet.

Link: [Get-DistributionGroup on Microsoft Technet](http://technet.microsoft.com/en-us/library/bb124755.aspx)  
Link: [–Filter Parameter on Microsoft Technet](http://technet.microsoft.com/en-us/library/bb430744.aspx)