---
title: Flujos multiusuario en bases de datos espaciales
author: Gabriel Corrales
date: '2021-06-03'
slug: flujos-multiusuario-en-bases-de-datos-espaciales
categories: []
tags:
  - Bases de datos espaciales
  - SIG
  - QGIS
  - ArcGIS
  - Multiusuario
subtitle: 'Capacidades que ofrecen las bases de datos espaciales para la implementación de flujos de trabajo en entornos multiusuario'
summary: 'Capacidades que ofrecen las bases de datos espaciales para la implementación de flujos de trabajo en entornos multiusuario.'
authors: 
        - admin
        - Ana Lucía Garita Fernández
lastmod: '2021-09-18T14:14:24-06:00'
featured: true
image:
  caption: ''
  focal_point: ''
  placement: ''
  preview_only: false 
projects: []
---
Los SIG (sistemas de información geográfica) son sistemas integradores de tecnología informática, personas e información geográfica para capturar, analizar, almacenar y representar datos georreferenciados.

Al ser el almacenamiento parte fundamental de los SIG, las bases de datos juegan un papel muy importante en estos sistemas, de ahí que la mayoría de los actuales SGBD (Sistemas Gestores de Bases de Datos) permitan la incorporación de información geográfica. De esta manera se originan las **bases de datos espaciales**, para almacenar entidades del mundo real que ocupan un lugar en el espacio y mantienen relaciones espaciales entre ellas y el resto de elementos del entorno.

Son las bases de datos espaciales las que permiten la edición de estos elementos en entornos de trabajo multiusuario. La edición multiusuario se puede llevar a cabo de dos formas, la **edición no versionada**, que realiza ediciones y actualizaciones dinámicas de las capas sin la utilización de diferentes versiones de las tablas. Esta metodología se puede llevar a cabo mediante el uso de vistas, que son tablas virtuales que almacenan consultas como objetos, pero que en realidad sólo almacenan su definición y no los datos propiamente.

**La edición versionada**, por su parte, trabaja en diferentes versiones, aislando el trabajo en diferentes sesiones de edición que permiten la edición concurrente. Este método conserva una versión principal original o versión predeterminada.

La edición versionada es la forma más robusta de trabajo multiusuario. Requiere de una conexión con una base de datos relacional como *IBM DB2*, *Informix*, *Oracle*, *PostgreSQL* o *Microsoft SQL Server*, así como un administrador de bases de datos involucrado en el proceso, por lo que es el método más complicado de establecer.

En el desarrollo de este artículo se amplían los conceptos relacionados con la edición multiusuario en bases de datos espaciales y se realiza una comparación entre diferentes flujos de trabajo en entornos multiusuario no versionados: el trabajo con *PostgreSQL* junto con *QGIS*, y varias alternativas para el uso de conjuntos de datos distribuidos entre múltiples geodatabases de archivos en *ArcGIS*, software de *ESRI*, la empresa líder mundial en sistemas de información geográfica.

Esta comparación se llevó a cabo a través de la realización de un ejemplo práctico del flujo de trabajo entre *PostgreSQL* y *QGIS*. Mientras que, en el caso del flujo de trabajo en *ArcGIS*, el ejemplo mostrado se obtuvo a partir de investigación bibliográfica.

Este trabajo pretende, mediante esta comparación, distinguir los flujos de trabajo en edición no versionada, además de proveer a los lectores, a través de ejemplos prácticos, un paso a paso en cada ambiente, así como identificar las ventajas de cada uno de ellos.

{{< icon name="download" pack="fas" >}} Descargar {{< staticref "uploads/Flujos_multiusuario.pdf" "newtab" >}}artículo{{< /staticref >}}.