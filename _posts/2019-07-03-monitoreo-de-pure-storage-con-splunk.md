---
layout: single
title:  "Monitoreo de Pure Storage con Splunk"
categories: recovery monitoreo
tags: splunk monitoreo purestorage drp
date:   2019-07-03 12:50:23 -0400
classes: wide
---
Todos saben que Pure Storage trae su propia herramienta y servicio de monitoreo 7×24 incluido en el equipamiento (**Pure1**). Pero qué pasa si en nuestra compañía tenemos  **Splunk** como herramienta corporativa y queremos ver la información de estos equipos allí o bien hacer correlación de eventos con los del Pure?

Para eso hay una solución ya que Pure se integra directamente a Splunk a través de un Plugin disponible en el portal de Splunkbase.

**Pure Storage TA**  (  [https://splunkbase.splunk.com/app/3659/](https://splunkbase.splunk.com/app/3659/)  )

Nos permite hacer la conexión con el arreglo de discos y traer los logs por medio del REST API de Pure Storage. Para la configuración basta con introducir la IP del arreglo, usuario y contraseña como un nuevo Data Input (por cada arreglo que tengamos) y empezará a recolectar información.

**Pure Storage App**  (  [https://splunkbase.splunk.com/app/3660/](https://splunkbase.splunk.com/app/3660/)  )

Es la App donde nos entrega los Dashboards por defecto y que podemos usar ni bien terminamos de instalarlas. A partir de aquí podemos hacer las querys o búsquedas que querramos e incluso generar la correlación de eventos que requerimos.

   [![](https://www.cuatroi.com/wp-content/uploads/2019/07/splunk3-1030x395.jpg)](https://www.cuatroi.com/wp-content/uploads/2019/07/splunk3-1030x395.jpg)
    
   [![](https://www.cuatroi.com/wp-content/uploads/2019/07/splunk2.jpg)](https://www.cuatroi.com/wp-content/uploads/2019/07/splunk2.jpg)
    
   [![](https://www.cuatroi.com/wp-content/uploads/2019/07/splunk1-1030x572.jpg)  
    ](https://www.cuatroi.com/wp-content/uploads/2019/07/splunk1-1030x572.jpg)
    [![](https://www.cuatroi.com/wp-content/uploads/2019/07/splunk-pure.jpg)](https://www.cuatroi.com/wp-content/uploads/2019/07/splunk-pure.jpg)