---
title: "Configuracion"
date: 2018-12-15T14:35:25-03:00
draft: false
---
## Instalación de SQLite

Para hacer los ejercicios y experimentar con el lenguaje SQL utilizaremos el sistema de base de datos SQLite desde la línea de comandos. La instalación de SQLite es muy simple y no requiere la configuración ni de un servidor ni de un cliente.

Utiliza el siguiente link para la descarga del software de SQLite https://www.sqlite.org/download.html. Selecciona los binarios precompilados apropiados para tu sistema operativo. En el caso de Windows te recomiendo descargar `sqlite-tools-win32-x86-3260000.zip
(1.68 MiB).`

Para instalar SQLlite:

1. Crea una nueva carpeta. Te recomiendo `C:\sqlite`
2. Extrae en dicha carpeta el contenido del archivo que acabas de descargar. Deberías ver el archivo `sqlite3.exe` en la carpeta `sqlite`.


Para verificar la instalación abre la línea de comando y navega hasta la carpeta `c:\sqlite`

```cmd
cd \sqlite
```

Luego tipea:

```cmd
sqlite3
```

Si todo anduvo bien, deberías ver algo similar a lo siguiente:

```cmd
SQLite version 3.26.0 2018-12-01 12:34:55
Enter ".help" for usage hints.
Connected to a transient in-memory database.
Use ".open FILENAME" to reopen on a persistent database.
sqlite>
```

Para salir de SQLite utiliza el comando .quit

```cmd
.quit
```

{{% notice note %}}
**Felicitaciones!** Ya tienes preparado tu entorno para experimentar con el lenguaje SQL y resolver los ejercicios del curso de base de datos. Ve por un <i class='fas fa-coffee'></i> !
{{% /notice %}}
