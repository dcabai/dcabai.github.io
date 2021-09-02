---
layout: single
title:  "Cómo hacer que SCVMM 2008 R2 Soporte Linux RH como Guest"
categories: microsoft 
tags: microsoft scvmm hyperv legacy
date:   2010-03-30 05:50:23 -0400
classes: wide
---
Por defecto System Center Virtual Machine Manager 2008 R2 con Microsoft Hyper-V no soporta Red Hat Linux como sistema operativo Guest. Osea Hyper-V si lo soporta pero a través de SCVMM 2008 R2 no aparece la opción de Red Hat, si aparece “SUSE” y “Other Linux”. La idea es hacer una pequeña modificación para que si aparezca la opción ya que Hyper-V si lo soporta.  
  
Ahora luego de creada la máquina si vamos a ver la opción de Red Hat Linux, pero cuando la seleccionamos en una VM existente podemos encontrarnos con un error similar al siguiente:  
  
**Error**  (10637)  
The virtualization software on host HOSTNAME does not support the Red Hat Enterprise Linux 5 operating system. 
{: .notice}
 
**Recommended Action**
Specify a host with different virtualization software and then try the operation again.  
{: .notice--warning}

Microsoft ya está al tanto de este pequeño error o bug pero todavía no hay un fix oficial al parecer, así que mientras tanto si necesitan usar este feature deberían realizar una actualización directamente sobre las tablas de la base de datos SQL al ejecutar la siguiente query:

```sql
update tbl_IL_OS
set OSFlags=0x14
where Name like 'Red Hat Enterprise Linux 5%'
```
Esta query debe ser ejecutada sobre la base de datos SQL que utiliza la instancia de SCVMM. Ahí van a encontrar la base **VirtualManagerDB** con la tabla **dbo.tbl_IL_OS**. Parado en esa tabla deben seleccionar **New Query** y copiar el código que puse mas arriba, luego ejecutarla. 

Esto cambia dos líneas en la tabla **tbl_IL_OS** con el atributo **OSFlags** para Red Hat de **16** (Hex 0x10) a **20** (Hex 0x14).  

Luego de esta modificación podremos cambiar una VM existente a Linux Red Hat sin ningun mensaje de error y además se podrá crear una nueva máquina con ese SO sin problemas ya que aparecerá dentro de la lista de SO soportados.

Link | [Hyper-V Guest Operating System Support](http://technet.microsoft.com/en-us/library/cc794868%28WS.10%29.aspx)