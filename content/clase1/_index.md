+++
title = "Clase 1"
date = 2018-11-30T20:58:36-03:00
weight = 10
+++


{{<mermaid>}}
gantt
        dateFormat H
        title HOJA DE RUTA
        Introducción            :      des1, 19, 15m
        El modelo relacional    :      des2, after des1 , 30m
        Break                   :      des3, after des2, 30m
        Consultando RDBMSs      :      des4, after des3, 25m
        El lenguaje SQL         :      des5, after des4, 20m
        Ejercitación            :crit, des6, after des5, 1h
{{< /mermaid >}}


## Introducción

A las bases de datos y a los sistemas de administración de bases de datos solemos representarlos gráficamente de la siguiente manera:

![Base de Datos](basededatos.png?width=10pc)

Pero...

##### Qué es una base de datos?

> _Una base de datos es una colección de datos gestionada por un sistema de administración de base de datos._

##### Y qué es un sistema de administración de base de datos?

> _Un sistema de administración de bases de datos (DBMS) proporciona acceso multiusuario a cantidades masivas de datos persistentes de manera eficiente, confiable, conveniente y segura._

{{% notice tip %}}
**DBMS** es la sigla en inglés de Data Base Management System. En español se suele usar la sigla **SGBD** (Sistema de Gestión de Base de Datos). En este curso optamos por las siglas en inglés para referirnos a este tipo de sistemas.
{{% /notice %}}

Nos encontramos con siete adjetivos:

1. "Multiusuario"
2. "Masivo"
3. "Persistente"
4. "Eficiente"
5. "Confiable"
6. "Conveniente"
7. "Seguro"

Veamos en detalle cada uno de estos siete adjetivos que determinan a un sistema de administración de base de datos.
