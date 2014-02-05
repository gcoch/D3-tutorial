---
layout: default
title: Instalación
permalink: "instalacion.html"
---

## Instalación

###Descargue de D3

Para comenzar, es necesario crear un directorio para su proyecto. Dentro de ese directorio, se recomienda crear un subdirectorio bajo el nombre **d3**, descargar la [versión más reciente](http://d3js.org/) de D3 y descomprimir el archivo ZIP. 

D3 también viene en un formato "comprimido" disponible en el [repositorio de Github](https://github.com/mbostock/d3). Este archivo no tiene espacio en blanco, por lo cual es de menor tamaño y se carga más rápidamente. 

Una tercera opción consiste en descargar el repositorio entero, con lo cual se obtiene no solamente los archivos de JavaScript sino también todo el código fuente de los componentes. Igualmente, puede revisar el contenido del repositorio o descargarlo todo como un archivo comprimido en formato ZIP.

###Referenciar a D3

Empiece creando un archivo simple en formato HTML de nombre *index.html*. La estructura del directorio debe ser similar a:

    project-folder/
        d3/
            d3.js
            d3.min.js (opcional)
        index.html

Luego, copie el siguiente código a su archivo HTML, de tal manera que éste haga referencia a D3 en la sección -head- y deje un espacio para el código de JavaScript:


    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="utf-8">
        <title>D3 Test</title>
        <script type="text/javascript" src="d3/d3.v3.js"></script>
    </head>
    <body>
        <script type="text/javascript">
            // Su código de D3 se incluirá acá
        </script>
    </body>
    </html>  

### Despliegue de la Página

En algunos casos, es posible abrir el archivo directamente desde el navegador. Sin embargo, cuando se cargan archivos externos es recomendable correr un servidor de web y visualizar la página desde **http://localhost:8888/**. Existen opciones como [MAMP](http://mamp.info/en/) o [SimpleHTTPServer](http://www.pythonforbeginners.com/modules-in-python/how-to-use-simplehttpserver/).

[Siguiente: Añadir Elementos -->]({{site.url}}/anadir-elementos.html)