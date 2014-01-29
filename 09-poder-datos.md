---
layout: default
title: La Función data( )
permalink: "data.html"
---
##El Poder de la Función data( )

Lo último que hicimos fue un diagrama de barras simple, dibujado utlizando etiquetas `div`y un conjunto de datos sencillo.

    var dataset = [ 5, 10, 15, 20, 25 ];
    
![Alt text]({{site.url}}/images/barra2.png) 

Está bien, pero los datos en la vida real nunca son así. Cambiemos [nuestros datos](http://alignedleft.com/content/03-tutorials/01-d3/90-the-power-of-data/2.html)

    var dataset = [ 25, 7, 5, 26, 11 ];

![Alt text]({{site.url}}/images/barras4.png)
    
Tampoco vamos a limitarnos a cinco datos. Podemos [añadir más](http://alignedleft.com/content/03-tutorials/01-d3/90-the-power-of-data/3.html)!

    var dataset = [ 25, 7, 5, 26, 11, 8, 25, 14, 23, 19,
                14, 11, 22, 29, 11, 13, 12, 17, 18, 10,
                24, 18, 25, 9, 3 ];
 

![Alt text]({{site.url}}/images/barras5.png)

25 datos en vez de cinco! Cómo es que D3 expande automáticament nuestro diagrama si es necesario?

    d3.select("body").selectAll("div")
    .data(dataset)  // <-- The answer is here!
    .enter()
    .append("div")
    .attr("class", "bar")
    .style("height", function(d) {
        var barHeight = d * 5;
        return barHeight + "px";
    });

Se le pasan diez datos a la función `data()`, ésta recorrerá la cadena diez veces. Si se le pasan un millón de datos, la recorrerá un millón de veces (solo tiene que tener paciencia).

Este es el poder de la función `data()`, la cual es lo suficientemente inteligente para recorrer por completo cualquier conjunto de datos que se le dé y ejecutar cada una de las funciones siguientes en la cadena. Esto lo hace mientras actualiza el contexto dentro del cual opera cada función, de tal manera que `d` siempre se refiere al dato actual, o aquel dónde esté el ciclo (loop) en ese momento.

Puede que esto sea demasiada información. Si no la entiende del todo en este momento, pronto la entenderá. Le recomiendo que guarde el código fuente de las páginas HTML de ejemplo anteriores, cambie los valores del conjunto de datos y revise cómo cambia el diagrama de barras.

Recuerde, los datos son lo que generan la visualización y no al contrario.

###Datos Aleatorios

Algunas veces es divertido generar conjuntos con datos aleatorios, pero efectos de chequeo o solamente por interés en temas técnicos. [Eso es lo que he hecho acá](http://alignedleft.com/content/03-tutorials/01-d3/90-the-power-of-data/4.html). Puede ver cómo cambia la gráfica cada vez que se refresca la página.

![Alt text]({{site.url}}/images/barras6.png)

![Alt text]({{site.url}}/images/barras7.png)

![Alt text]({{site.url}}/images/barras8.png)

Si revisa el código fuente, podrá ver:
    var dataset = [];                        //Initialize empty array
    for (var i = 0; i < 25; i++) {           //Loop 25 times
        var newNumber = Math.random() * 30;  //New random number (0-30)
        dataset.push(newNumber);             //Add new number to array
        }

Este código no utiliza ningún método de D3, es solamente JavaScript. Sin entrar en mucho detalle, este código:

1. Crea un arreglo vacío denominado `dataset`.
2. Inicia un ciclo (loop) `for`, que se ejecuta 25 veces.
3. Por cada ciclo, se genera un número aleatorio entre 0 y 30.
4. El nuevo número se añade al arreglo `dataset`. (`push()`es un método de arreglos que añade un nuevo valor al final del arreglo.)

Solamente por jugar, abra la consola de JavaScript y escriba `console.log(dataset)`. Podrá ver todo el arreglo con 25 valores generados aleatoriamente.

![Alt text]({{site.url}}/images/random.png)

Puede ver que todos los números son decimales o puntos flotantes (14.793717765714973) y no números reales o enteros (14) como usamos inicialmente. Para efectos de este ejemplo, esto basta, pero si alguna vez necesita números enteros, puede usar el método de JavaScript `Math.round()`. Por ejemplo, se puede envolver el generador de números aleatorios de esta línea:

    var newNumber = Math.random() * 30;
    así:
    var newNumber = Math.round(Math.random() * 30);
    
[Pruébelo aquí](http://alignedleft.com/content/03-tutorials/01-d3/90-the-power-of-data/5.html) y use la consola para verificar que los números se hayan redondeado a números enteros.

Ahora vamos a expandir las posibilidades de visualización con SVG.



[Siguiente: Introducción a SVG -->]({{site.url}}/intro-svg.html)