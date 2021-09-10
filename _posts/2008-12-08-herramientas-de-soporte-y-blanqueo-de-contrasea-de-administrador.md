---
layout: single
title:  "Herramientas de Soporte y Blanqueo de Contraseña de Administrador"
categories: microsoft 
tags: microsoft windows server legacy
date:   2008-12-08 05:50:23 -0400
classes: wide
---

Cuantas veces tuvimos que dar soporte a un servidor y no nos acordamos la contraseña de administrador local o la del dominio? Pero eso no es lo unico cuantas veces tuvimos que buscar alguna forma de reiniciar en modo DOS para hacer alguna tarea sobre el servidor? Creo que si el que lee esto es un administrador la respuesta va a ser “más de las que me gustaría”. En esta oportunidad entonces voy a mostrarles algunas de las formas de dar soporte o hacer tareas sobre los servidores iniciando con un CD de Herramientas de Soporte. Voy a mostrarles tres opciones de las que existen en el mercado, las tres son gratuitas y se van actualizando.  
  
La idea es mostrar algunas imagenes y tareas que pueden aparecer al iniciar el servidor con estos CDs. Por ejemplo, es muy común que me pregunten como blanquear una contraseña de administrador, cuáles son los pasos? bueno la idea es mostrarles algunos de los pasos y derivarlos a los sitios de los creadores de dichas herramientas para que puedan obtener mas información como así también documentación de los productos.  
  
Para esto armé un laboratorio con un Windows 2003 Server Standard Edition con Service Pack 2 y posteriores parches de seguridad. Es miembro de un Grupo de Trabajo y con una clave de Administrador default. La idea es mostrar algunas de las herramientas y posterior cómo blanquear la contraseña.  
  
**Ultimate Boot CD for Windows (UBCD4Win)**  
Con este producto primero debemos bajarlo e instalarlo. La imagen que crea es a partir del BartPE que ya había comentado antes en este sitio para crear una imagen booteable desde un CD de Windows. Si vas a necesitar los binarios de Windows para crearlo así que te sugiero que los tengas a mano.  
  
Los pasos para instalarlo y crear la imagen son bastantes simples y sencillos solo debemos ir siguiendolos y podremos armar la imagen.  
  
![image-left](/assets/images/HerramientasdeSoporteyBlanqueodeContrase_D770/image.png "UBCD4Win"){: .align-left}   ![image-left](/assets/images/HerramientasdeSoporteyBlanqueodeContrase_D770/image_3.png "UBCD4Win"){: .align-left}   
  
Una vez instalado y pasado todo el setup de creación de imagen y al bootear con ella veremos las siguientes pantallas. Obviamente sabemos que este en particular al iniciar es un Windows así que vamos a tener modo gráfico si es que vamos por defecto. Lo primero que nos va a preguntar es si queremos configurar la red, luego podemos seguir con lo que querramos hacer. También existen otras opciones para iniciar que las comento luego de las pantallas.  
  
![image-left](/assets/images/HerramientasdeSoporteyBlanqueodeContrase_D770/image_4.png "UBCD4Win"){: .align-left}   ![image-left](/assets/images/HerramientasdeSoporteyBlanqueodeContrase_D770/image_5.png "UBCD4Win"){: .align-left}  
  
Este producto tiene muchísimas herramientas para probar y testear. Tiene de todo, herramientas de red, de disco, de sistema, antivirus, para editar el registro, etc. Es uno de los mas completos que conozco.  
Si no iniciamos en el modo gráfico por defecto vamos a encontrar otros productos muy interesantes para iniciar, por ejemplo:  
  
Darik’s Boot and Nuke: Es una utilidad que borra todo el contenido de un disco para que no pueda ser recuperado.  
Memtest86: Chequeo completo de memoria de un equipo.  
NTFS for DOS: Inicio en modo DOS con soporte NTFS.  
Offline NT Password & Registry Editor: Un poderoso blanqueador de contraseñas para Windows que comento particularmente mas abajo ya que se puede hacer un CD aparte con esta herramienta.  
Windows Recovery Console: La conocida consola de recuperación de Windows.  
  
Link: [Ultimate Boot CD for Windows](http://www.ubcd4win.com/)  
  
**SystemRescueCD**  
Es un CD booteable en Linux pensado para solucionar algunos problemas en tu equipo luego de una caída. No tiene tantas herramientas como tal vez otras soluciones pero tiene editores de texto, navegadores web, manejador de archivos, particionador de discos y puede leer unidades NTFS. Si juntamos eso mas que tiene un editor entonces podemos hasta editar el registro de Windows.  
  
Al iniciar con el CD veremos una pantalla como la siguiente, toda basada en Linux y al finalizar podemos seguir trabajando en base a comandos o si no estamos acostumbrados podemos ejecutar el comando “wizard” y configuraremos un modo gráfico para trabajar.  
  
![image-left](/assets/images/HerramientasdeSoporteyBlanqueodeContrase_D770/image_6.png "SystemRescueCD boot"){: .align-left}  ![image-left](/assets/images/HerramientasdeSoporteyBlanqueodeContrase_D770/image_7.png "SystemRescueCD boot"){: .align-left}  
  
El modo gráfico no es de otro mundo pero tiene los accesos y utilidades básicas y necesarias para poder trabajar. Creo que si tu objetivo es editar el registro, copiar archivos o particionar es una excelente opción.  
  
![image-left](/assets/images/HerramientasdeSoporteyBlanqueodeContrase_D770/image_8.png "SystemRescueCD GUI"){: .align-left}  ![image-left](/assets/images/HerramientasdeSoporteyBlanqueodeContrase_D770/image_9.png "SystemRescueCD GUI"){: .align-left}  
  
En la página también explica como instalar esta solución en un dispositivo USB así no dependemos del CD, sólo que el equipo debería soportar este tipo de booteo. Otro tema que siempre se toca son los drivers de las placas de Storage, pero si no viene incluído, simple es un Linux agregalo a la imagen del CD y listo.  
  
Link: [SystemRescueCD HomePage](http://www.sysresccd.org/Main_Page)  
Link: [Lista Completa de Herramientas en el CD](http://www.sysresccd.org/System-tools)  
  
**NT Offline Password and Registry Editor**  
Este producto viene en versión de diskette y CD pero obviamente ya se usa unicamente el de CD. Podemos grabar directamente el producto en un CD o bien utilizar el que viene en el primer producto comentado. Este si es un producto 100% linux y no posee interfaz gráfica así que si no estas a gusto con ella no te queda otra. :)  
  
![image-left](/assets/images/HerramientasdeSoporteyBlanqueodeContrase_D770/image_10.png "NT Offline Password and Registry Editor"){: .align-left}

Los pasos son simples, primero iniciamos con el CD y veremos una pantalla como la de la izquierda. Lo primero que debemos hacer si no vemos los discos listados con un número es cargar los drivers adecuados. En el sitio hay un montón de drivers que podemos cargar al CD si no está el adecuado podemos bajarlo de internet y agregarlo. Con la letra **d** hacemos que detecte automáticamente los discos a cargar. Si no puede encontrarlo entonces debemos usar la letra **m** para cargar el driver manualmente. Con la **l** volvemos a listar las particiones NTFS/FAT disponibles y con la **a** muestra todas. Una vez que vemos el disco listado seleccionamos el número, en este caso el 1 ya que hay una sola. Luego nos pregunta el directorio config de Windows para ver si lo tenemos en otra ruta y al continuar nos pregunta si queremos resetear una contraseña o iniciar una recovery console con opciones.  
  
Al seleccionar 1 para blanquear la contraseña del administrador nos pregunta si queremos editar alguna entrada del registro o modificar usuarios y contraseñas. Seleccionamos **1** para editar usuarios y contraseñas y nos va a mostrar una lista de los usuarios que podemos blanquear, en este caso el Administrador que lo selecciona por defecto. Luego nos pregunta qué queremos hacer con la cuenta porque tal vez esté bloqueada simplemente y la podemos desbloquear o bien blanquearla usando como opción el asterisco (*****)  y listo.  
  
Link: [Offline NT Password and Registry Editor](http://home.eunet.no/pnordahl/ntpasswd/)