---
layout: single
title:  "Chau CloudEndure. Hola AWS Elastic Disaster Recovery"
categories: aws cloud
tags: cloud aws backup drp 
date:   2022-12-14 12:00:00 -0400
classes: wide
---

CloudEndure era la oferta de solución ante desastres de AWS, sin embargo, el 1ro de Septiembre de 2023 ya no podrás registrar nuevas cuentas en CloudEndure. El 1ro de Diciembre de 2023 ya no podras instalar nuevos agentes y el 31 de Marzo de 2024 será **discontinuado** definitivamente.

Por ese motivo, debemos migrar a AWS Elastic Disaster Recovery cuanto antes en caso de tener CloudEndure en nuestra organización. Afortunadamente hay una herramienta para hacer la migración, es la **CEDR to DRS Upgrade Assessment Tool** y la **Server Upgrade Tool**.  Documentación de las herramientas: Link: [Upgrading from CEDR to DRS](https://docs.cloudendure.com/#Configuring_and_Running_Disaster_Recovery/Upgrade_CEDR_to_DRS/Upgrade_CEDR_to_DRS.htm#Upgrading_from_CEDR_to_AWS%C2%A0DRS%3FTocPath%3DNavigation%7CConfiguring%2520and%2520Running%2520Disaster%2520Recovery%7CUpgrading%2520from%2520CEDR%2520to%2520AWS%25C2%25A0DRS%7C_____0)
También hay un video de cómo se realiza dicha migración. Link: [Upgrade from CEDR to AWS DRS](https://www.youtube.com/watch?v=r9hY90vGpnM)

AWS Elastic Disaster Recovery es una solución de recuperación ante desastres basada en la nube que permite a las empresas recuperar rápida y fácilmente sus sistemas y aplicaciones de TI en caso de desastre. Esta solución está diseñada para ser altamente escalable, confiable y rentable, lo que la convierte en una opción atractiva para empresas de todos los tamaños.

En este post, te detallo las características principales y los beneficios clave de AWS Elastic Disaster Recovery.

### Características clave de AWS Elastic Disaster Recovery:
- **Automated Recovery**: Automatiza el proceso de recuperación de sistemas y aplicaciones. En caso de desastre, el sistema lanza automáticamente instancias de recuperación en la nube de AWS, que luego se utilizan para restaurar datos y aplicaciones.
- **Scalability**: la solución es altamente escalable y se puede adaptar para satisfacer las necesidades de empresas de todos los tamaños. Puede manejar una amplia gama de cargas de trabajo y se puede ampliar o reducir fácilmente según sea necesario.
- **Reliability**: Está diseñado para ser altamente confiable. Utiliza múltiples zonas de disponibilidad para garantizar que los datos estén siempre disponibles y tiene funciones integradas que detectan y se recuperan automáticamente de fallas.
- **Cost-Effective**: la solución está diseñada para ser rentable, con precios basados en el uso. Esto significa que las empresas solo pagan por los recursos que utilizan, lo que la convierte en una opción atractiva para empresas con diferentes necesidades.

### Cómo funciona AWS Elastic Disaster Recovery:
AWS Elastic Disaster Recovery funciona mediante la creación de una réplica de los sistemas y aplicaciones en la nube de AWS. Como funciona a nivel de sistema operativo, no importa si el origen está virtualizado en VMware, Hyper-V o es una máquina física.
En caso de desastre, lanza automáticamente instancias de recuperación en la nube. Estas instancias se utilizan para restaurar datos y aplicaciones desde la réplica, lo que permite a las empresas volver a funcionar rápidamente.
Para configurarlo primero debes crear un plan de recuperación. Este plan describe los pasos que se tomarán en caso de un desastre, como qué aplicaciones se recuperarán y en qué orden.
Una vez que el plan de recuperación está implementado, puedes usar AWS Elastic Disaster Recovery para crear una réplica de tus sistemas y aplicaciones. Esta réplica se puede actualizar regularmente para garantizar que permanezca sincronizada con el sistema principal.

### Conclusión:
AWS Elastic Disaster Recovery es una solución altamente escalable, confiable y rentable para las empresas que necesitan recuperar rápidamente sus sistemas y aplicaciones en caso de desastre. Al crear una réplica de sus sistemas y aplicaciones en la nube de AWS, las empresas pueden asegurarse de estar siempre preparadas para el peor de los casos. Con recuperación automatizada, múltiples zonas de disponibilidad y precios flexibles, es una herramienta poderosa para cualquier empresa que valore la resiliencia y la continuidad. Es el homólogo de Azure Site Recovery para los que actualmente poseen dicha nube.

Link: [AWS Elastic Disaster Recovery](https://aws.amazon.com/disaster-recovery/)
Link: [Documentación AWS Elastic Disaster Recovery (AWS DRS)](https://docs.aws.amazon.com/drs/latest/userguide/what-is-drs.html)
Link: [Comparativa CloudEndure – AWS Elastic Disaster Recovery](https://aws.amazon.com/disaster-recovery/when-to-choose-aws-drs/?cloud-endure-blogs.sort-by=item.additionalFields.createdDate&cloud-endure-blogs.sort-order=desc)
Link: [CloudEndure EOL FAQ](https://docs.cloudendure.com/Content/FAQ/FAQ/CloudEndure_DR_EOL_FAQ.htm)