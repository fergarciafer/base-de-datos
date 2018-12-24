+++
title = "Clase 1"
date = 2018-11-30T20:58:36-03:00
weight = 10
+++


{{<mermaid>}}
gantt
        dateFormat H
        title HOJA DE RUTA
        Introducción            :      des1, 19, 30m
        El modelo relacional    :      des2, after des1 , 30m
        Consultando RDBMSs      :      des3, after des2, 30m
        Break                   :      des4, after des3, 30m
        Ejercitación            :crit, des5, after des4, 1h
{{< /mermaid >}}


## Introducción

Lo sepas o no es muy probable que estés interactuando con bases de datos varias veces por día. Hoy en día hay bases de datos presentes en todos lados. Puedes encontrarlas detrás de muchos sitios web, en los sistemas bancarios, en los sistemas de telecomunicaciones, en implementaciones de sensores, y en muchos otros lugares más.

A las bases de datos y a los sistemas de administración de bases de datos solemos representarlos gráficamente de la siguiente manera:

![Base de Datos](basededatos.png?width=10pc)

Y a continuación nos haremos dos preguntas...

##### Qué es una base de datos?

> _Una base de datos es una colección de datos gestionada por un sistema de administración de base de datos._

##### Y qué es un sistema de administración de base de datos?

> _Un sistema de administración de bases de datos (DBMS) proporciona acceso multiusuario a cantidades masivas de datos persistentes de manera eficiente, confiable, conveniente y segura._

{{% notice tip %}}
**DBMS** es la sigla en inglés de Data Base Management System. En español se suele usar la sigla **SGBD** (Sistema de Gestión de Base de Datos). En este curso optamos por las siglas en inglés para referirnos a este tipo de sistemas.
{{% /notice %}}

En esta definición nos encontramos con siete adjetivos:

1. "Multiusuario"
2. "Masivo"
3. "Persistente"
4. "Eficiente"
5. "Confiable"
6. "Conveniente"
7. "Seguro"

Veamos en detalle cada uno de estos adjetivos que determinan a un sistema de administración de base de datos.

**Multiusuario**. Múltiples usuarios pueden estar operando simultáneamente sobre la misma base de datos. Muchas aplicaciones pueden acceder a los datos de forma concurrente. El DBMS cuenta con mecanismos de control de concurrencia que aseguran que los datos permanezcan consistentes y no haya interacciones inesperadas entre los usuarios. El control de concurrencia tiene alguna similitud al control de concurrencia que se puede hacer a nivel de archivos o variables; pero en este caso se centra en los datos.

**Masivo**. Un DBMS está preparado para manejar datos a escala masiva. Hoy en día un DBMS puede gestionar terabytes de datos, o  incluso terabytes de datos generados diariamente.

**Persistente**. Los datos de una base de datos sobreviven a los programas que se ejecutan y utilizan dichos datos. En la ejecución de un programa informático típico, creamos y operamos con variables; y cuando el programa finaliza las variables desaparecen. En un DBMS los datos trascienden a los programas. Los programas se inician y terminan, pero los datos permanecen en el DBMS.

**Eficiente**. Los DBMS ejecutan miles de consultas o actualizaciones por segundo. Y dichas consultas no son necesariamente simples; sino que pueden resultar ser operaciones muy complejas. Por lo tanto, construir un sistema de base de datos que pueda ejecutar consultas  complejas a ese ritmo, sobre enormes cantidades de datos no es una tarea simple; y esa es una de las principales características que proporciona un sistema de administración de bases de datos.

**Confiable**. Es de vital importancia que un sistema de base de datos esté en funcionamiento prácticamente todo el tiempo. Es crítico que un DBMS sea fiable estando prácticamente disponible todo el tiempo para sus usuarios y aplicaciones.

**Conveniente**. La conveniencia es quizá una de las características más críticas de los sistemas de administración de bases de datos. Un DBMS está diseñado para que resulte fácil trabajar con grandes cantidades de datos. En las bases de datos existe un concepto conocido como "Independencia física de los datos". Lo que nos dice este concepto es que la manera en que pensamos las estructuras de los datos es independiente de la forma en que los datos están realmente almacenados y dispuestos en disco. Así, las bases de datos suelen ser consultadas con lenguajes declarativos de muy alto nivel. En las consultas que realizamos describimos qué datos queremos sin necesidad de especificar un algoritmo que determine cómo obtener dichos datos. Podemos escribir consultas de una forma muy sencilla, y luego el sistema mismo encontrará el algoritmo para obtener el resultado de manera eficiente.

**Seguro**. Un DBMS garantiza que los datos administrados por el sistema permanecerán en un estado coherente y no se perderán ni se sobreescribirán cuando haya fallas de hardware o software; e incluso simples cortes de energía. Por lo tanto, los sistemas de bases de datos incluyen una serie de mecanismos integrados que garantizan que los datos permanecen consistentes, independientemente de lo que suceda.

***

Hay cuatro conceptos clave que cubriremos a continuación.

El primer concepto clave el de **modelo de datos**. El modelo de datos es una descripción general de como se estructuran los datos en una base de datos. Uno de los modelos de datos más comunes y populares es el llamado modelo de datos relacional. En el modelo relacional los datos se manejan como conjuntos de registros. Sin embargo, esta no es la única forma de estructurar los datos. Otra forma de estructurarlos es utilizando XML. En XML los datos se manejan con estructuras jerárquicas etiquetadas. Otro modelo es el grafos en los que los datos se estructuran como nodos y aristas.

El segundo concepto clave es el de **esquema vs datos**. El esquema determina la estructura de la base de datos. Quizá en mi base de datos maneje una estructura de clientes y proveedores, con sus direcciones de correo electrónico y teléfonos de contacto. Esa estructura será el esquema que luego alojará los datos de cada uno de mis clientes y proveedores. En general, el esquema se configura al principio y no cambia con demasiada frecuencia. Quizá en algún momento quiera agregar algún atributo adicional de mis clientes como podría ser la edad. En cambio los datos cambian con mucha mas frecuencia, agregamos nuevos clientes todos los días y los proveedores nos entregan nuevos productos todas las semanas.

A continuación entra el tercer concepto clave. Para configurar el esquema, se suele utilizar lo que se conoce como **lenguaje de definición de datos**. A veces se utilizan herramientas de diseño de nivel superior que ayudan a pensar el diseño y luego el diseño se materializa mediante el lenguaje de definición de datos. En síntesis, el lenguaje de definición de datos se usa para configurar un esquema o estructura de una base de datos en particular.

Una vez configurado el esquema es posible comenzar a ingresar, consultar y modificar datos. Normalmente esas operaciones se hacen con lo que se conoce como **lenguaje de manipulación de datos**.

{{% notice tip %}}
En general nos referimos al lenguaje de definción de datos como **DDL** y al lenguaje manipulación de datos como **DML**. Esto se debe a sus siglas en inglés "Data Definition Language" y "Data Manipulation Language" respectivamente.
{{% /notice %}}

***

Existen distintos roles que toman las personas según la forma en que se involucran con una base de datos.

El **implementador** es la persona que construye un DBMS. El contenido de este curso no está enfocado en este rol. Si tu idea es crear un nuevo DBMS, entonces los temas contenidos en este curso serán necesarios pero no suficientes para tí.

Luego está el **diseñador** de la base de datos. El diseñador establece el esquema para una base de datos. Supongamos que tenemos que desarrollar una aplicación y queremos determinar cómo vamos a estructurar los datos antes de construirla. Ese es el trabajo del diseñador de la base de datos. Es un trabajo sorprendentemente difícil cuando tienes una aplicación que involucra información muy compleja.

 Una vez establecida la estructura de la base de datos, hay que construir la aplicación y desarrollar los programas que se ejecutarán sobre la base de datos, interactuando entre el usuario final y los datos en sí. Ese es el trabajo del **desarrollador**.

 Por último encontramos al **administrador de la base de datos**. Es quien pone en funcionamiento a la base de datos y la mantiene funcionando sin problemas. Este es trabajo muy importante sobre todo cuando implica bases de datos grandes. Los sistemas de bases de datos suelen contar con una serie de parámetros de ajuste asociados, y hacer que esos parámetros sean adecuados pueden marcar una diferencia significativa en el rendimiento de un DBMS. Es por eso que los administradores de bases de datos son altamente valorados, y suelen estar muy bien pagados.

 {{% notice tip %}}
 Es muy común referirse al administrador de base de datos con el término **DBA**. El origen de dicho término está determinado por las siglas en inglés de Data Base Administrator.
 {{% /notice %}}

 En este curso nos enfocaremos principalmente en contenidos que tienen que ver principalmente con el diseño y desarrollo de aplicaciones. Veremos algunos temas que tienen que ver con la administración, pero en general pensando desde la perspectiva del desarrollador de aplicaciones y usuario de la base de datos.

***

## El modelo relacional

El modelo relacional nació hace más de 40 años cuando el científico informático inglés Ted Codd propuso que los sistemas de bases de datos debían presentarle los datos a los usuarios en vistas organizadas como tablas. A dichas vistas organizadas como tablas, Codd las llamó **relaciones**. Detrás de escena podrían existir estructuras de datos complejas que permitieran dar respuesta rápida a diversidad de consultas. Pero a diferencia de los sistemas de bases de datos anteriores el usuario de la base de datos no debería preocuparse por dichas estructuras de almacenamiento. Las consultas podrían expresarse en un lenguaje de alto nivel haciendo más eficiente el trabajo de los programadores. A lo largo de este curso profundizaremos en SQL, el lenguaje más importante basado en el modelo relacional.

Hoy en día, el modelo relacional es el más difundido del mundo con un gran número de implementaciones comerciales eficientes. Es un modelo extremadamente simple y ofrece la posibilidad de consultar la base de datos utilizando el lenguaje SQL.

La construcción primaria del modelo relacional es la **relación**. Una base de datos está conformada por un conjunto de relaciones, también llamadas **tablas**. Una relación es una tabla de dos dimensiones conformadas por filas y columnas. Veamos esto con un ejemplo. Nuestro ejemplo será una base de datos de álbumes musicales. Aquí comenzaremos con una tabla de álbumes.

![Tabla](Tabla.png?width=20pc)

 Luego tenemos el concepto de **atributo**. Cada relación tiene un conjunto predefinido de columnas o atributos, cada uno de los cuales tiene un nombre. Para nuestra tabla de álbumes, cada álbum tiene los siguientes atributos: identificación (AlbumId), título y tapa.

 ![Tabla y Columnas](TablaYColumnas.png?width=30pc)

A continuación, los datos reales se almacenan en **tuplas** o **filas** de la tabla.  Cada atributo o columna de la tabla tiene un **tipo** (a veces denominado **dominio**). Por ejemplo, el identificador del álbum puede ser un número entero, el nombre puede ser una cadena de caracteres, la tapa puede ser un archivo png.

Al nombre de la relación junto al conjunto de atributos que la definen se los conoce como **esquema** de la relación. Al conjunto de esquemas de todas las relaciones de la base de datos se lo llama esquema de base de datos.

 ![Tuplas](Tuplas.png?width=30pc)

Existe un valor especial que está en cualquier tipo de cualquier columna conocido como **nulo**. El concepto de nulo es muy importante en las bases de datos relacionales. Los valores nulos se utilizan para denotar que un valor particular puede ser desconocido o no definido.

Otro concepto importante en las bases de datos relacionales es el **clave**. Una clave es un atributo en una relación donde cada valor para ese atributo es único. Entonces, si nos fijamos en la relación de los álbumes, podemos estar casi seguros de que el identificador del álbum será una clave. En otras palabras, cada tupla de la relación álbumes tendrá un identificador único. Puede que te estés preguntando por qué es importante tener atributos que se identifican como claves. En realidad, a las claves se le pueden dar varios usos. Uno de ellos es solo para identificar tuplas específicas. Por lo tanto, si desea ejecutar una consulta para obtener una tupla específica de la base de datos, lo haría solicitando esa tupla por su clave. Otro uso posible es el de los **índices**. Los índices son estructuras que se pueden utilizar en las bases de datos y que permiten encontrar muy rápido tuplas específicas.

Veamos ahora cómo se crean relaciones o tablas en el lenguaje SQL. Es muy simple:

``` sql
CREATE TABLE "albums"
(
    [AlbumId] INTEGER,
    [Title] NVARCHAR(160)
);
```

A medida que vayamos avanzando en el curso iremos viendo con mucho más detalle todos estos conceptos.

***

## Consultando bases de datos relacionales

Veamos a continuación los pasos básicos para crear y utilizar una base de datos relacional.
El primer paso es diseñar el esquema de la base de datos y luego crear el esquema usando un lenguaje de definición de datos. El esquema consiste en la estructura de las relaciones y los atributos de esas relaciones.
El siguiente paso es cargar la base de datos con los datos iniciales. Es bastante común que la base de datos se cargue inicialmente a partir de datos que provienen de una fuente externa. Una vez cargados los datos, tenemos un montón de tuplas en nuestras relaciones.
Ahora, estamos listos para consultar y modificar datos. Luego vamos a tener usuarios humanos que consultan directamente a la base de datos. Eso suele suceder a través de una aplicación o un sitio web; aparecerá un usuario, hará una consulta a la base de datos y obtendrá una respuesta. También habrá usuarios que quieran insertar nuevos datos o actualizar algunos de los datos.
Ese es el paradigma básico de consultar y actualizar bases de datos relacionales.

En todos los lenguajes de consulta relacionales, cuando realizas una consulta a través de un conjunto de relaciones, se obtiene una relación como resultado. El álgebra relacional es un lenguaje formal que está muy bien fundamentado teóricamente. Por el contrario, SQL es un lenguaje real o implementado. Ese es el que se va a ejecutar en una aplicación de base de datos implementada real. Pero el lenguaje SQL tiene como base el álgebra relacional.

***

## Ejercitación

Para la mayor parte de los ejercicios de este curso hemos elegido el DBMS **SQLite**.

SQLite es una librería desarrollada en lenguaje C que implementa un DBMS SQL pequeño, rápido, autónomo y de alta confiabilidad. SQLite es el DBMS más utilizado del mundo. Está integrado en prácticamente todos los teléfonos móviles y en una gran cantidad de computadoras. También suele estar incluido en infinidad de otras aplicaciones que la gente usa diariamente.

SQLite no es comparable a los DBMS SQL cliente / servidor tradicionales, como MySQL, Oracle, PostgreSQL o SQL Server. Por qué motivo no es comparable? SQLite trata de resolver problemas diferentes.

Los motores de base de datos SQL cliente / servidor se esfuerzan por implementar un repositorio compartido de datos empresariales. Hacen énfasis en la escalabilidad, la concurrencia, la centralización y el control. SQLite se esfuerza por proporcionar almacenamiento de datos local para aplicaciones y dispositivos individuales. SQLite hace énfasis en la economía, la eficiencia, la confiabilidad, la independencia y la simplicidad.

Para este curso hemos elegido SQLite debido a que es fácil de configurar y usar. Es un buen DBMS para aprender SQL. Como estudiante vas a poder crear fácilmente tantas bases de datos como quieras y podrás incluso intercambiarlas por correo electrónico con tus compañeros o instructores para hacer comentarios o revisiones. Adicionalmente, si tu interés es estudiar cómo se implementa un RDBMS, el código SQLite modular, bien comentado y documentado puede servir como una buena base para tu estudio.

Si aún no has configurado tu ambiente de trabajo, éste es el momento! Recuerda que hemos dejado un instructivo de instalación de SQLite en la sección [Configuración](../configuracion)

***

Una vez que hayas preparado el ambiente de trabajo y antes de introducirnos en la práctica del lenguaje SQL, es necesario que te familiarices con algunos comandos propios de la interface de SQLite (sqlite3).

El proyecto SQLite proporciona un programa de línea de comandos llamado `sqlite3` que permite al usuario ingresar y ejecutar manualmente sentencias SQL contra una base de datos SQLite. A continuación hacemos una breve introducción al uso del programa `sqlite3`.

Inicia el programa escribiendo `sqlite3` desde la línea de comandos, opcionalmente seguido del nombre del archivo que contiene la base de datos SQLite. Si el archivo nombrado no existe, se creará automáticamente un nuevo archivo de base de datos con el nombre provisto. Si no se especifica ningún archivo de base de datos en la línea de comandos, se crea una base de datos temporal que se eliminará cuando el programa `sqlite3` finalice su ejecución.

Para iniciar `sqlite3` con la base provista en el curso para la resolución de los ejercicios dirígete a la carpeta que contiene el programa:

```cmd
c:\>cd c:\sqlite
```

Luego ejecuta el comando `sqlite3` seguido del nombre del archivo que contiene la base de datos provista para la ejercitación:

```cmd
c:\sqlite>sqlite3 chinook.db
SQLite version 3.26.0 2018-12-01 12:34:55
Enter ".help" for usage hints.
sqlite>
```

Al iniciarse, el programa `sqlite3` mostrará un breve mensaje y quedará a la espera de la próxima instrucción.

{{% notice tip %}}
Puedes presionar `CONTROL+C` para interrumpir la ejecución de `sqlite3`
{{% /notice %}}

Generalmente `sqlite3` leerá las líneas de entrada y las pasará a la librería SQLite para su ejecución. Sin embargo, las líneas de entrada que comienzan con un punto (".") son interceptadas e interpretadas por el propio programa `sqlite3`. Estos "comandos de punto" también llamados **dot commands** se usan normalmente para cambiar el formato de salida de las consultas o para ejecutar ciertas instrucciones de consulta preempaquetadas.

Para obtener una lista completa de los comandos de punto disponibles, puedes ingresar `.help` sin argumentos. O ingresa `.help COMANDO` para obtener información detallada sobre COMANDO:

```cmd
sqlite> .help
.archive ...             Manage SQL archives
.auth ON|OFF             Show authorizer callbacks
.backup ?DB? FILE        Backup DB (default "main") to FILE
...
...
...
.vfsname ?AUX?           Print the name of the VFS stack
.width NUM1 NUM2 ...     Set column widths for "column" mode
sqlite>
```

Algunas reglas para los comandos de punto:

- Un comando de punto debe comenzar con el `.` en el margen izquierdo sin espacios en blanco precedentes.
- El comando de punto debe estar completamente contenido en una sola línea de entrada.
- Un comando de punto no puede ocurrir en medio de una instrucción SQL ordinaria.
- Los comandos de punto no reconocen comentarios.
- Los comandos de punto son interpretados por el programa de línea de comandos sqlite3.exe, no por el propio SQLite.

{{% notice note %}}
Es muy importante que puedas establecer la diferencia entre los comandos del lenguaje SQL y los comandos propios de la interface de SQLite. A estos últimos se los conoce como **dot commands** y se caracterizan por comenzar con el caracter "punto". Los comandos de punto son directamente ejecutados por el programa `sqlite3`, mientras que los comandos del lenguaje SQL son ejecutados por la librería SQLite invocada desde `sqlite3` al submitir la instrucción.
{{% /notice %}}

`sqlite3` proporciona varios comandos que son útiles para observar el esquema de la base de datos. Por ejemplo, para ver una lista de las tablas en la base de datos, puedes ingresar `.tables`.

```cmd
sqlite> .tables
albums          employees       invoices        playlists
artists         genres          media_types     tracks
customers       invoice_items   playlist_track
sqlite>
```

El comando `.indexes` lista todos los índices. Si al comando `".indexes` se le agrega el nombre de una tabla como argumento, muestra solamente los índices pertenecientes a dicha tabla.

```cmd
sqlite> .indexes employees
IFK_EmployeeReportsTo
sqlite>
```
El comando ".schema" muestra la estructura completa de la base de datos, o de una sola tabla si se proporciona un argumento con el nombre de tabla:

```cmd
sqlite> .schema albums
CREATE TABLE IF NOT EXISTS "albums"
(
    [AlbumId] INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL,
    [Title] NVARCHAR(160)  NOT NULL,
    [ArtistId] INTEGER  NOT NULL,
    FOREIGN KEY ([ArtistId]) REFERENCES "artists" ([ArtistId])
                ON DELETE NO ACTION ON UPDATE NO ACTION
);
CREATE INDEX [IFK_AlbumArtistId] ON "albums" ([ArtistId]);
sqlite>
```

Ahora que ya estás familiarizado con la interface y algunos de los comandos de punto más importantes, avancemos con el lenguaje SQL!

***

Cuando escribas código SQL, asegúrate de finalizar el comando con un punto y coma. El programa `sqlite3` busca un punto y coma para saber cuándo finaliza un comando SQL. Si se omite el punto y coma, `sqlite3` lo interpretará como una solicitud de continuación en la siguiente línea y esperará a que ingreses más texto. Esta es una característica que te permite ingresar comandos SQL que abarcan varias líneas. Presiona `Enter` para ejecutar la instrucción. Por ejemplo:

```cmd
sqlite> select lastname from employees;
Adams
Edwards
Peacock
Park
Johnson
Mitchell
King
Callahan
sqlite>
```

```cmd
sqlite> select lastname
   ...> from employees;
Adams
Edwards
Peacock
Park
Johnson
Mitchell
King
Callahan
sqlite>
```
