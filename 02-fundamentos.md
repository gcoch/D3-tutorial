---
layout: default
title: Fundamentos
permalink: "fundamentos.html"
---

## Fundamentos

Para trabajar con D3 es indispensable tener conocimiento de los siguientes conceptos:

###HTML
Hypertext Mark Language se utiliza para organizar el contenido que muestran los navegadores de internet.

La página más sencilla de HTML es algo así:

    <html>
        <head>
            <title>Título de la Página</title>
        </head>
        <body>
            <h1>Capítulo 1</h1>
            <p>Este es un párrafo importante</p>
        </body>
    </html>

###DOM
El DOM (Modelo de Objetos del Documento) ser refiere a la estructura jerárquica de HTML. Cada una de las etiquetas corresponde a un elemento, y los elementos están relacionados entre sí. Para describir estas relaciones se usan los mismos términos con los que se describen las generaciones humanas: padre, hijo, hermano(a), ancestro y descendiente. En el código HTML anterior, **body** es el elemento padre de los hijos **h1** y **p**, los cuales a su vez son hermanos. Todos los elementos de la página son descendientes de **html**.

Los navegadores de la red descomponen el DOM para interpretar el contenido de la página.


###CSS

Las hojas de estilo en cascada se usan para definir el estilo que se utilizará para mostrar las páginas de HTML. A continuación se muestra un ejemplo simple de un archivo CSS:

    body {
        background-color: white;
        color: black;
    }

Los estilos de un CSS están compuestos de selectores y reglas. Selectores identifican elementos específicos a los cuales se les aplicarán los estilos. 

    h1          /* Selecciona los títulos de primer nivel  */
    p           /* Selecciona párrafs                      */
    .caption    /* Selecciona elementos de clase "caption" */
    #subnav     /* Selecciona elemento con ID "subnav"     */

Reglas son propiedades que en conjunto crean los estilos:

    color: pink;
    background-color: yellow;
    margin: 10px;
    padding: 25px;

Los selectores y reglas se conectan usando llaves:

    p {
        font-size: 12px;
        line-height: 14px;
        color: black;
    }

D3 utiliza el mismo estilo de los selectores en CSS para identificar elementos a los cuales se les aplicará alguna operación, por consiguiente es importante entender cómo se usan.

Las reglas de CSS se pueden incluir usando la etiqueta -head- de la siguiente manera:

    <head>
        <style type="text/css">
            p {
                font-family: sans-serif;
                color: lime;
                }
        </style>
    </head>

También se pueden guardar en un archivo externo con el sufijo .css, para luego referenciarlo dentro de documento, usando la etiqueta  -head- , de la siguiente manera:

    <head>
        <link rel="stylesheet" href="style.css">
    </head>


###JavaScript

JavaScript en un lenguaje de programación interpretado, mediante el cual se pueden enviar instrucciones al navegador con el propósito de cambiar la página después de que se haya descargado.

Los programas (scripts) se pueden incluir directamente dentro del HTML, utilizando las etiquetas -script-, de la siguiente manera:

    <body>
        <script type="text/javascript">
            alert("Hello, world!");
        </script>
    </body>


También se pueden guardar en otro archivo, el cual debe ser referenciado en algún lugar dentro del HTML (usualmente en la sección -head- ), de la siguiente manera:

    <head>
        <title>Page Title</title>
        <script type="text/javascript" src="myscript.js"></script>
    </head>

###Herramientas de Desarrollo

Es importante familiarizarse con las herramientas de desarrollo del navegador. En los navegadores WebKit (como Safari o Chrome), es posible abrir el inspector de web, tal como se ve en la siguiente gráfica:

![Alt text]({{site.url}}/images/web-inspector.png)

La opción de "View Source" o ver código muestra el código HTML original. Más importante aún es el inspector de web, pues a través de esta opción es posible verificar el *estado actual del DOM*. Así, es posible revisar cómo los programas generan cambios en forma dinámica sobre los elementos. También es posible utilizar la Consola de JavaScript para depurar el código.


###SVG

D3 brilla en área de despliegue de gráficas en formato SGV (Scalable Vector Graphics). SVG es un formato que utiliza texto para desplegar imágenes. Esto se refiere a que una imagen SVG puede ser definida utilizando código de etiquetas, de forma similar a HTML. En realidad, el código SVG se puede integrar dentro de cualquier documento HTML. Los navegadores de la web han incluido soporte para este formato durante muchos años (con excepción de Internet Explorer), sin embargo solo recientemente ha empezado a tener aceptación.

Este es un pequeño círculo codificado dentro de la página.

<svg width="50" height="50">
    <circle cx="25" cy="25" r="22"
     fill="blue" stroke="gray" stroke-width="2"/>
</svg>


    <svg width="50" height="50">
        <circle cx="25" cy="25" r="22"
        fill="blue" stroke="gray" stroke-width="2"/>
    </svg>

Inténtelo - oprima sobre el círculo y verá que no es una imagen! Amplíe la pantalla (zoom) y verá cómo cambia de escala de manera gradual, tal como lo debe hacer una gráfica en formato vectorial .

El uso de formato SVG no es un requisito en D3, sin embargo SVG proporciona una serie de facilidades de despliegue visual que simplemente no son factibles de replicar con elementos HTML. 

[Siguiente: Instalación -->]({{site.url}}/instalacion.html)