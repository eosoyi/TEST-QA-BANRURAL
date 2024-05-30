# Plan de Estrategia de Pruebas para el Juego de Adivinar el Número

## Introducción

Este documento detalla el plan de estrategia de pruebas para el juego de adivinar el número, destacando los errores encontrados y las soluciones aplicadas. El objetivo es asegurar que el juego funcione correctamente y que los mensajes de estado se muestren adecuadamente según las reglas especificadas.

## Objetivos de las Pruebas

1. Validar que el número a adivinar sea un entero positivo entre 1 y 100.
2. Asegurar que el número ingresado por el jugador sea un entero positivo.
3. Verificar que se muestren los mensajes correctos en el color adecuado para cada escenario:
   - Acierto del número.
   - Número mayor al número a adivinar.
   - Número menor al número a adivinar.
   - Derrota después de 10 intentos.
4. Comprobar que los intentos no se incrementen cuando se ingrese un valor no válido.
5. Verificar que el juego se reinicie correctamente después de una victoria o derrota.

## Alcance de las pruebas
Las pruebas se centrarán en las funcionalidades principales del juego, incluyendo la generación del número aleatorio, la validación del número ingresado por el usuario, los mensajes de feedback y el reinicio del juego.

## Escenarios de Prueba

### Prueba 1: Generación del Número Aleatorio
- **Descripción:** Verificar que el número aleatorio generado esté entre 1 y 100.
- **Acción:** Revisar el valor de `randomNumber` en la consola.
- **Resultado Esperado:** El número debe ser un entero entre 1 y 100.

### Prueba 2: Validación del Número Ingresado

- **Descripción:** Verificar que solo se acepten enteros positivos.
- **Acción:** Ingresar varios valores no válidos (e.g., texto, números negativos, decimales).
- **Resultado Esperado:** Se debe mostrar una alerta y no debe incrementarse el contador de intentos.

### Prueba 3: Mensaje y Color para Intentos Fallidos

- **Descripción:** Verificar que se muestren los mensajes correctos en color negro cuando el número ingresado es mayor o menor que el número a adivinar.
- **Acción:** Ingresar valores mayores y menores que el número aleatorio.
- **Resultado Esperado:** Se deben mostrar los mensajes "Incorrecto! El número es mayor!" o "Incorrecto! El número es menor!" en color negro.

### Prueba 4: Mensaje y Color para Victoria y Derrota

- **Descripción:** Verificar que se muestren los mensajes de victoria y derrota en los colores correctos.
- **Acción:** Adivinar el número correctamente y agotar los 10 intentos sin adivinar.
- **Resultado Esperado:** El mensaje de victoria debe ser "Felicitaciones! adivinaste el número!" en color verde. El mensaje de derrota debe ser "!!!Pérdistes!!!" en color rojo.

### Prueba 5: Reinicio del Juego

- **Descripción:** Verificar que el juego se reinicie correctamente después de una victoria o derrota.
- **Acción:** Completar un juego (victoria o derrota) y presionar el botón de reinicio.
- **Resultado Esperado:** El juego debe reiniciarse con un nuevo número aleatorio y los campos de entrada deben estar habilitados.


## Errores encontrados
# **Error en la Validación del Número Ingresado:**
**Descripción:** No se validaba que el número ingresado por el usuario fuera un entero positivo.
**Solución:** Se implementó la función isPositiveInteger para validar si el número ingresado es un entero positivo. Si no lo es, se muestra una alerta y se evita incrementar el contador de intentos.


# **Error en los Mensajes de Feedback para Intentos Fallidos:**
**Descripción:** Los mensajes de feedback para intentos fallidos no se mostraban correctamente
**Solución:** Se actualizó la lógica de la función checkGuess para mostrar los mensajes "Incorrecto! El número es mayor!" y "Incorrecto! El número es menor!" en color negro cuando el usuario falla.


# **Error de Capitalización en addEventListener:**
**Descripción:** La función addEventListener estaba escrita incorrectamente como addeventListener.
**Solución:** Se corrigió la capitalización a addEventListener en todos los lugares donde se utilizaba.


# **Error en los Mensajes de Victoria y Derrota:**
**Descripción:** Los mensajes de victoria y derrota no se mostraban con los colores correctos.
**Solución:** Se actualizaron los colores de los mensajes de victoria (verde) y derrota (rojo) en la función checkGuess.

## Herramientas de Prueba

- **Navegador Web:** Para ejecutar y probar el juego en un entorno real.
- **Consola del Navegador:** Para verificar la generación de números aleatorios y depurar mensajes.

## Conclusión

Este plan de estrategia de pruebas está diseñado para asegurar que el juego de adivinar el número funcione correctamente según las especificaciones dadas. Se recomienda realizar todas las pruebas enumeradas para garantizar una experiencia de usuario satisfactoria.
