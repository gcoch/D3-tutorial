---
layout: default
title: Añadir Elementos
permalink: "anadir-elementos.html"
---
##Añadir Elementos

Uno de los primeros pasos en el uso de D3 consiste en crear un nuevo elemento en el DOM. Por lo general, éste será un objeto SVG para desplegar una visualización gráfica de datos, sin embargo con el propósito de empezar con algo simple, a continuación se muestra cómo añadir un elemento -p-.

Se empieza con la siguiente plantilla de HTML.

    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="utf-8">
            <title>D3 Test</title>
            <script type="text/javascript" src="d3/d3.v3.js"></script>
        </head>
        <body>
            <script type="text/javascript">
            // Su bello código de D3 vendrá acá
            </script>
        </body>
    </html>

En [este enlace](http://alignedleft.com/content/03-tutorials/01-d3/40-adding-elements/1.html) puede ver la página generada por este código. No parece tener mucho, sin embargo al abrir el inspector de web, se puede ver lo siguiente.

![Alt text]({{site.url}}/images/pagina-demo.png)

Ahora, en el archivo HTML, cambie el texto dentro de las etiquetas **script** con el siguiente código:

**d3.select("body").append("p").text("New paragraph!");**

Guarde y refresque [o revise esta página](http://alignedleft.com/content/03-tutorials/01-d3/40-adding-elements/2.html) y verá el cambio! Ahora se muestra un texto en la ventana del navegador, y en el inspector de web se muestra lo siguiente:

![Alt text]({{site.url}}/images/pagina2-demo.png)

Nota la diferencia? Ahora el DOM contiene un nuevo elemento que se generó dinámicamente! Puede ser que esto no sea muy interesante aún, pero pronto podrá ver cómo con una técnica similarse pueden generar decenas o centenas de elementos, cada uno representando una parte de sus datos.

Miremos lo que acaba de ocurrir. Secuencialmente:

1. Se invocó el método **select** de D3, el cual selecciona un solo elemento en el DOM utilizando la sintaxis del selector en CSS. (En este caso se utilizó **body**).

2. Se creó un nuevo elemento **p** y se añadió al final de la selección, o sea justo *antes* de la etiqueta de cierre -body- en este caso.

3. Se actualizó el contenido del párrafo vacío con la frase "New Parragraph".

Al margen, todos esos puntos son parte de la *sintaxis de encadenamiento* de D3.

[Siguiente: Encadenar Métodos -->]({{site.url}}/encadenar-metodos.html)