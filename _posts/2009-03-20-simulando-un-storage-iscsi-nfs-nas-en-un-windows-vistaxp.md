---
layout: single
title:  "Simulando un Storage iSCSI, NFS, NAS en un Windows Vista/XP"
categories: microsoft 
tags: microsoft windows server legacy
date:   2009-03-20 05:50:23 -0400
classes: wide
---

Ya había comentado otro artículo para instalar un VMware ESX Server en una Workstation Windows Vista o XP. Pero no podemos usar el total de las funciones si no tenemos un Storage en la red. VMware soporta varios tipos de Storage, entre ellos está iSCSI, y un NAS NFS. Por suerte existen algunos simuladores o mejor dicho Storage Servers a base de Linux/FreeBSD que podemos montar de la misma forma que el VMware. Podemos instalarlo en un equipo virtual definitivo y hasta productivo o bien podemos usarlo a modo de testing con el mismo VMware Player como el VMware ESX Server.  
  
Para lo que voy a comentar también necesitamos el VMware Player instalado en nuestro equipo y lo pueden obtener de [este link](http://www.vmware.com/products/player/). Esta no es la única solución, si nosotros usamos Virtual Server lo podemos instalar ahí desde cero o bien si tenemos un ambiente con VMware en la red también lo podemos instalar ahí. Con esto quiero decir que no sólo sirve para simular o practicar un ambiente con Storage en la red sino que sirve como Storage Server en el ambiente que tengas hoy implementado.  
  
Las soluciones vienen de la mano de [FreeNAS](http://www.freenas.org/) y [Openfiler](http://www.openfiler.com/). Yo voy a comentar sólo el que usamos con VMware player en nuestro equipo, pero si lees la documentación vas a ver que no es muy complicado levantar cualquiera de las otras versiones.  
  

## FreeNAS

La versión actual al momento de escribir este artículo es la 0.69 y nos va a servir perfectamente para lo que necesitamos que es levantar un Storage en nuestra red y utilizarlo con VMware ESX para poder probar el VMotion, HA, DRS, etc.  
  
FreeNAS es una herramienta gratuita para levantar un NAS (Network Attached Storage) Server soportando NFS, iSCSI, CIFS, FTP, etc. De esto nosotros vamos a usar NFS e iSCSI ya que VMware no soporta CIFS. Para poder obtenerlo vamos al link “Download” y buscamos la versión “**FreeNAS VMware Images**”. Esta versión la vamos a poder usar con VMware Player sin tener que instalar nada adicional, sólo configurarla. Si queres instalar el producto de cero buscá la ISO del mismo en otro de los downloads disponibles. Al bajar el zip y descomprimirlo vamos a ver todos los archivos de una máquina virtual típica de VMware. Si ejecutamos el .vmx nos va a abrir el VMware Player con el servidor por defecto instalado. Al ejecutarlo nos va a preguntar si la VM la copiamos o la movimos, siempre debemos poner que la copiamos.  
  
![image-center](/assets/images/SimulandounStorageiSCSINFSNASenunWindows_98F9/image.png "freenas"){: .align-center}  
  
Cuando termina de levantar vamos a ver una pantalla similar a esta donde vemos que toma una IP del DHCP, vemos algunas opciones para seleccionar y vemos abajo la cantidad de discos que ya vienen mapeados por defecto y armados en la imagen VMware que bajamos y son los que vamos a usar con iSCSI y NFS luego en el ESX. Luego ingresamos mediante un Browser con usuario  **admin**  y contraseña  **freenas**  y vamos a ver la pantalla web de administración del producto.  
  
![image-center](/assets/images/SimulandounStorageiSCSINFSNASenunWindows_98F9/image_3.png "freenas"){: .align-center}![image-center](/assets/images/SimulandounStorageiSCSINFSNASenunWindows_98F9/image_4.png "freenas"){: .align-center}  
  
Luego sólo nos falta levantar y configurar los servicios que queremos tener activos. En nuestro caso NFS e iSCSI, pero si lo utilizas para tu casa por ejemplo está muy práctico el servicio de BitTorrent ya que podes tener un servidor FreeBSD dedicado a bajar Torrents y te conectas por NFS a los downloads por ejemplo.  
  
Bueno, siguiendo, vamos a  **Services**  –>  **NFS,** marcamos  **Enable**  y hacemos click en Save and Restart. Con esto el NFS ya está activo, sólo nos falta agregar un Share. Para esto vamos a  **Shares**  dentro de NFS, hacemos click en el  **+**, completamos los datos que nos pide, por ejemplo podemos usar el RAID1 que trae para esto poniendo  **/mnt/raid1/**  y luego Apply changes. Con esto ya tenemos nuestro NFS arriba y funcionando.  
  
Ahora con respecto a iSCSI, primero vamos a  **Services**  –>  **iSCSI Target**. Ahí debemos agregar los campos de Extent, Device y Target. En mi caso me funcionó mejor utilizando un  **File**  como Extent que un Device, pero para esto debemos tener el file creado ya en el File System. Luego de completar todos los datos lo habilitamos y nos va a generar la dirección iSCSI que es algo como iqn.year-mo.reversed_domain_name:unique_name. Copiamos ese nombre y vamos a  **Disks**  –> **Management**  –>  **iSCSI Initiator**  y completamos los datos y luego lo habilitamos. Con todo esto ya podemos usar el disco iSCSI que acabamos de crear en el VMware ESX.  

## Openfiler

El Openfiler es un poco mas bonito gráficamente pero en si cumple con las mismas funciones que el FreeNAS. Es otra opción gratuita para poder generar un NAS en la red. Actualmente al momento de este artículo la versión que existe es la 2.3. Para empezar tenemos que ir a  **Download Openfiler**  de su página web. Ahí tenemos diferentes opciones como en el caso de FreeNAS y seleccionamos la de VMware ESX para poder usarla con el VMware Player.  
  
Al descomprimir el archivo ZIP vamos a ver que esta versión pesa mucho mas que la de FreeNAS pero la performance de un disco flat es mucho mejor que la de uno dinámico. La web de administración la vamos a ver un poco mas linda que la de FreeNAS pero son servicios similares. Una vez que levanta cuando ejecutamos el vmx vemos la siguiente pantalla.  
  
![image-center](/assets/images/SimulandounStorageiSCSINFSNASenunWindows_98F9/image_5.png "openfiler"){: .align-center}  
  
Acá no vamos a ver tantos discos conectados como con el FreeNAS porque funciona de diferente manera, pero la administración también es web al igual que el anterior. Usamos para iniciar sesión el usuario  **openfiler** y contraseña  **password**.  
  
![image-center](/assets/images/SimulandounStorageiSCSINFSNASenunWindows_98F9/image_6.png "openfiler"){: .align-center}  ![image-center](/assets/images/SimulandounStorageiSCSINFSNASenunWindows_98F9/image_7.png "openfiler"){: .align-center}  
  
Para empezar a trabajar debemos ir a  **Volumes**  y ahí debemos crear un nuevo volumen en el disco /dev/sdb. Los servicios que vamos a habilitar nuevamente son NFSv3 e iSCSI. Los pasos son similares, debemos crear los volumenes, montarlos, compartirlos, etc. Los pasos exactos estan en los PDF de ambos productos, pero lo importante es que podemos utilizar alguno de estos dos sistemas para levantar un Storage NAS o NSA en nuestra red.  
  
Sinceramente tuve mejores resultados con el primer ejemplo “FreeNAS” pero es la decisión de cada uno y las pruebas de cada uno lo que va a decidir qué opción tomar. Recuerda que también puedes instalarlo desde cero y no usar las imágenes que ya vienen cargadas en la web.  
  
Lo importante es que lo podamos montar en nuestro VMware ESX Server para poder hacer prácticas. Esto siempre pensando en un ambiente de testing, para producción te recomiendo que uses las ISO y los instales desde cero. Pero bueno, si ya tenemos nuestro NFS e iSCSI en la red debemos ir a VMware y montarlo, tan simple como eso.  
  
En cuanto al Storage iSCSI debemos agregar primero la placa VMkernerl para el Storage y luego debemos agregar el iSCSI con la IP que nos tiró FreeNAS u Openfiler. Para el caso de NFS directamente agregamos el Storage necesario con la ruta del NFS.