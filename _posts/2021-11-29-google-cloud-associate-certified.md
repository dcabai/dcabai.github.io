---
layout: single
title:  "Google Cloud Certified - Associate Cloud Engineer"
categories: gcp cloud
tags: cloud gcp multicloud kubernetes certificacion exam
date:   2021-11-29 12:50:23 -0400
classes: wide
---

![image-left](/assets/images/google-associate/badge.png){: .align-left} Finalmente rendí el examen de **Google Cloud** antes de finalizar el 2021 para así al menos contar con una certificación en cada uno de los grandes hyperscalers. Esto no termina acá pero para poder tener una visión multicloud y para poder seguir en la consultoría de este tipo de arquitecturas era vital contar con certificaciones en los tres.

En términos de Marketshare se puede decir que Google Cloud Platform o GCP está en tercer lugar por debajo de Azure y AWS sigue cómodo primero, pero GCP es mas una nube de términos específicos que de propósitos generales y ahí es donde destaca. Su servicio de **Bigquery** es increíble. El manejo de los datos realmente se destaca en esta nube y de más mencionar la integración con **Kubernetes**.

### Ahora a lo importante, qué me pareció este examen?

El primero que daba de Google, la plataforma de examen de Kryterion, es algo diferente a las de Microsoft, VMware o incluso AWS, la vi un poco mas básica. La seguridad de los auditores del examen fue algo "excesiva" a mi parecer y al finalizar el examen pasó algo curioso que no me había pasado en los fabricantes anteriores, me dijo algo así como "Pasaste el examen, pero vamos a revisar la filmación nuevamente así que espera 10 días hábiles el resultado oficial." jajajaja Me pareció lo mas **manual** y poco automatizado del planeta viniendo de una entidad que entrega examenes de tecnología e innovación.

Pero el resultado llegó oficialmente, por eso no lo comenté antes, estaba esperando que revisen la grabación :)
Este examen es de preguntas del tipo multiple choice, no hay que escribir o desarrollar respuestas ni tampoco labs como en otros examenes. Es uno de los mas básicos de esta nube, pero debo decir que es mas profundo que los básicos de otras nubes. No "amplio" sino "profundo" en algunos temas.

Otras nubes te toman muchos mas servicios y el para que sirve, en el caso de Google te pregunta por menos servicios, los mas importantes, pero te pide llegar mas a fondo en esos temas.

Para registrarse deben crear una cuenta en Webassessor/Kryterion, el link está abajo en este mismo post.

![image-center](/assets/images/google-associate/diploma.png){: .align-center}

### Qué estudiar?

No puedo comentar mucho sobre el contenido del examen por la política de privacidad que todos los que alguna vez rendimos uno, conocemos. Pero si puedo decirles qué estudiar, qué temas mas se tocan, darles algunos links y recursos que les puede ser útil a la hora de practicar o ir a rendir el examen.  

Necesitas algo de práctica. Si pensabas en leer el manual e ir a rendir, la vas a pasar mal. Necesitas práctica y conocer los productos ya que como dije es mas profunda que amplia. 

La certificación mas básica es **Cloud Digital Leader**, esta es similar a la de Cloud Practitioner de AWS. La que rendí yo es la segunda, similar a la de Asociado de AWS y Azure. Es un paso para luego poder pasar a la de Arquitecto y las de especializaciones.

- Me preguntaron mucho sobre cuentas/organizaciones y carpetas.
- Para qué sirven los productos en general, osea cuándo se usa Cloud Spanner, Cloud SQL, etc.
- Logging y monitoreo también hubieron bastantes preguntas, acerca del uso de Stackdriver y demás.
- Kubernetes de todas maneras, con los accesos ingress y egress y cuando se usa cada uno.
- Utilización de imagenes de cómputo, registry de contenedores.
- Políticas y accesos IAM.

Ojo, no significa que sólo te vayan a tomar esto, sino que eso fue lo mas recurrente en MI examen. También debes recordar que las preguntas no son las mismas para todos.

Les dejo algunos lugares con buenos cursos y labs para tomar, algunos tienen material gratuito, otros son pagos.

- [Udemy](https://www.udemy.com/)
- [A Cloud Guru](https://acloudguru.com/)
- [CloudAcademy](https://cloudacademy.com/)
- [Qwiklabs](https://www.qwiklabs.com/)
- [Coursera](https://www.coursera.org/)

Linkes generales:

Link: [Google Cloud Certification](https://cloud.google.com/certification)
Link: [Google Associate Cloud Engineer](https://cloud.google.com/certification/cloud-engineer)
Link: [Google Associate Cloud Engineer Smaple Questiosn](https://docs.google.com/forms/d/e/1FAIpQLSfexWKtXT2OSFJ-obA4iT3GmzgiOCGvjrT9OfxilWC1yPtmfQ/viewform)
Link: [Google Associate Cloud Engineer Exam Guide](https://cloud.google.com/certification/guides/cloud-engineer?skip_cache=true)

Documentación que tuve que leer mas en detalle ya que como dije, algunos temas van al detalle (fondo) y uno en el día a día esos detalles los busca a la hora de implementar, pero me sirvió para repasar ciertos puntos que me tomaron en el examen. Lean a consciencia ya que de nuevo, los detalles, son los que aparecieron en el examen.  
  
Link: [Storage Classes](https://cloud.google.com/storage/docs/storage-classes)  
Link: [gcloud config](https://cloud.google.com/sdk/gcloud/reference/config)  
Link: [SSL Proxy Load Balancing overview](https://cloud.google.com/load-balancing/docs/ssl)  
Link: [VPC network overview](https://cloud.google.com/vpc/docs/vpc#manually_created_subnet_ip_ranges)  
Link: [Using Stackdriver Workspaces](https://cloud.google.com/blog/products/management-tools/using-stackdriver-workspaces-help-manage-your-hybrid-and-multicloud-environment)  
Link: [Monitoring Multiple Projects with Cloud Monitoring](https://www.cloudskillsboost.google/focuses/621?parent=catalog&qlcampaign=77-818-workspace-51)  
Link: [Monitoring with Cloud Monitoring](https://cloud.google.com/spanner/docs/monitoring-cloud)  
Link: [Setting up health checking and autohealing](https://cloud.google.com/compute/docs/instance-groups/autohealing-instances-in-migs)  