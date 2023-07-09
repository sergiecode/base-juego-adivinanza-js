## Link al curso completo de Javascript en Youtube:
[VIDEO CURSO GRATIS COMPLETO: JavaScript Desde Cero por Sergie Code](https://youtu.be/N8Xt5rP_DUo)


# Tutorial de Javascript: Juego de Adivinanza

Link para ver el resultado: [JUEGO ADIVINANZA TRABAJO TERMINADO](https://juego-adivinanza-tutorial-js.netlify.app/)

Este repositorio contiene el código de un juego de adivinanza implementado en Javascript. El juego consiste en adivinar un número aleatorio generado por el programa en un rango del 1 al 100.

## Código Javascript

El archivo Javascript principal es `script.js`, que contiene las siguientes funciones y variables:

### Generar un número aleatorio

    let numeroAzar = Math.floor(Math.random() * 100) + 1;

Esta línea de código genera un número aleatorio entre 1 y 100 y lo guarda en la variable `numeroAzar`. Utilizamos `Math.random()` para generar un número decimal entre 0 y 1, luego lo multiplicamos por 100 para obtener un número entre 0 y 100, y finalmente utilizamos `Math.floor()` para redondear hacia abajo y obtener un número entero entre 0 y 99. Al sumar 1 al resultado, obtenemos un número aleatorio entre 1 y 100.

### Obtener elementos del DOM

    let numeroEntrada = document.getElementById('numeroEntrada');
    let mensaje = document.getElementById('mensaje');

Estas líneas de código obtienen referencias a los elementos del Document Object Model (DOM) utilizando el método `getElementById()`. El elemento con el id "numeroEntrada" representa el campo de entrada donde el usuario ingresa su número, y el elemento con el id "mensaje" muestra mensajes de retroalimentación al usuario.

### Función para comprobar el número ingresado

    function chequearResultado() {
        let numeroIngresado = parseInt(numeroEntrada.value);
    
        if (isNaN(numeroIngresado) || numeroIngresado < 1 || numeroIngresado > 100) {
            mensaje.textContent = 'Por favor, introduce un número válido entre 1 y 100.';
            return;
        }
    
        if (numeroIngresado === numeroAzar) {
            mensaje.textContent = '¡Felicidades! ¡Has adivinado el número correcto!';
            mensaje.style.color = 'green';
            numeroEntrada.disabled = true;
        } else if (numeroIngresado < numeroAzar) {
            mensaje.textContent = 'El número es mayor. Intenta de nuevo.';
            mensaje.style.color = 'red';
        } else {
            mensaje.textContent = 'El número es menor. Intenta de nuevo.';
            mensaje.style.color = 'red';
        }
    }

Esta función se llama cuando el usuario presiona el botón de "Comprobar". Primero, obtiene el número ingresado por el usuario utilizando `numeroEntrada.value` y lo convierte a un número entero utilizando `parseInt()`. Luego, verifica si el número ingresado es un número válido dentro del rango esperado (1-100). Si el número no es válido, se muestra un mensaje de error en el elemento "mensaje" y se devuelve de la función.

Si el número ingresado es válido, se compara con el número generado aleatoriamente. Si son iguales, se muestra un mensaje de felicitación y se deshabilita el campo de entrada. Si el número ingresado es menor que el número aleatorio, se muestra un mensaje indicando que el número es mayor. Si es mayor, se muestra un mensaje indicando que el número es menor. En ambos casos, el mensaje se muestra en el elemento "mensaje" y se cambia el color del texto al rojo.

## Uso del juego

1.  Clona o descarga este repositorio en tu computadora.
2.  Abre el archivo `index.html` en tu navegador web.
3.  Verás una interfaz de usuario con un campo de entrada y un botón de "Comprobar".
4.  Ingresa un número válido entre 1 y 100 en el campo de entrada y presiona el botón de "Comprobar".
5.  Dependiendo de tu número ingresado, recibirás mensajes indicando si el número es mayor o menor que el número aleatorio, o si has adivinado correctamente.
6.  Si adivinas correctamente, el campo de entrada se deshabilitará y se mostrará un mensaje de felicitación.

¡Diviértete jugando y practicando tus habilidades en Javascript!
