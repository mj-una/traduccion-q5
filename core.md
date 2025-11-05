# CORE

https://q5js.org/learn/#coreSection


Bienvenidx a la documentación de q5! 🤩

¿Primera vez programando? Revisa la [guía para principiantes de q5].

En estas páginas de "Aprender" puedes experimentar editando los mini ejemplos. ¡Diviértete! 😎



## draw()  
dibujar()

Función a declarar. Se ejecutará 60 veces por segundo de forma predeterminada. Tiene comportamiento de bucle, lo que permite hacer animaciones cuadro a cuadro.



## setup()  
iniciar()

Función a declarar. Se ejecutará una sola vez, al principio del sketch. Sirve para las configuraciones generales o dibujar un cuadro estático.

Puede declararse como función asíncrona y usarse para cargar recursos (ver ejemplo 2).



## preload()  
precargar()

Función a declarar. Se ejecutará por completo antes del inicio. Sirve para agrupar la carga de recursos (imagenes, sonidos, fuentes, etc) asegurándose de que queden listos para usarse.

Sin declarar un `preload` se puede lograr el mismo comportamiento si se crea el lienzo en "modo superficial" y luego se cargan los recursos (ver ejemplo 2), o si se usa un `setup` asíncrono (ver ejemplo 2 de `setup`).



## frameCount  
cuadroActual

Número del cuadro actual, es decir, la cantidad de cuadros que se han dibujado desde que se inició el sketch.



## noLoop()  
pausar()

Detiene el bucle de dibujo.



## redraw(n)  
redibujar(n)

Dibuja el lienzo `n` veces. Si no recibe parametro, se dibuja una sola vez. Útil para controlar animaciones con el bucle pausado.

**Parámetros**
- `n` <number> (opcional) - cantidad de veces que se volverá a dibujar el lienzo. Por defecto es 1.



## loop()  
reanudar()

Vuelve a activar el bucle de dibujo en caso de que estuviera pausado.



## frameRate(hz)  
frecuencia(hz)

Si recibe un parámetro, establece la cantidad ideal de cuadros que se intentarán dibujar por cada segundo (es decir, la tasa de refresco, la frecuencia del bucle).

Retorna la frecuencia real alcanzada durante el último segundo de ejecución. Incluso si nunca se modifica explícitamente la frecuencia, el valor real suele fluctuar entre el ideal y 0. Para un mejor análisis del rendimiento usar las herramientas del navegador (DevTools).

**Parámetros**
- `hz` <number> (opcional) - cantidad ideal de cuadros a dibujar en un segundo. Por defecto es 60.

**Retorno**
- <number> - frecuencia real del bucle en el último segundo.



## getTargetFrameRate()  
frecuenciaIdeal()

Retorna la cantidad ideal de cuadros que se intentan dibujar por segundo.

**Retorno**
- <number> - cantidad ideal de fotogramas por segundo.



## getFPS()  
frecuenciaMaxima()

Retorna la cantidad maxima de cuadros que se podrían estar dibujando en cada segundo.

Es un valor teórico que depende del estado del dispositivo. Para un mejor análisis del rendimiento usar las herramientas del navegador (DevTools).

**Retorno**
- <number> - cantidad máxima teorica de cuadros por segundo.



## log(message)  
log(mensaje)

Imprime un mensaje en la consola de JavaScript. Atajo para `console.log()`.

Para acceder a las herramientas del navegador (DevTools) generalmente es con click derecho + "inspeccionar", o presionando las teclas `ctrl + shift + i` o `command + option + i`. La consola se encuentra en la pestaña "console".

**Parámetros**
- `mensaje` <any> - mensaje a imprimir.



## postProcess()  
retocarDibujo()

Funcion a declarar. Se ejecuta después de cada llamada a `dibujar` y de los `hooks de dibujo`, pero antes de dibujar realmente el lienzo.

Útil para agregar efectos finales cuando es difícil hacerlo en la función de dibujo. Por ejemplo, al usar extensiones como p5play que dibujan capas superpuestas al lienzo.



## windowWidth  
anchoVentana

El ancho de la ventana (cantidad de píxeles). Atajo para `window.innerWidth`.



## windowHeight  
altoVentana

El alto de la ventana (cantidad de píxeles). Atajo para `window.innerHeight`.



## deltaTime  
ultimoTiempo

Milisegundos que han pasado desde el último cuadro dibujado. Con la frecuencia por defecto a 60 hz, el tiempo aproximado es 16.6 ms o mas.

Útil para mantener las animaciones sincronizadas con precisión, sobretodo si existen momentos en que la ejecución se ralentiza por sobrecarga del dispositivo. En casos en que la frecuencia real del bucle sea considerablemente mas baja, es recomendable reducir la frecuencia ideal.



## usePromiseLoading(val)  
usarPromesas(bandera)

Permite decidir si las funciones de carga (`loadImage`, `loadFont`, etc) retornan promesas o una referencia al recurso por cargar.

Al igual que en p5.js v1, las funciones `load*` por defecto retornan referencias. Pero si el `setup` se declara con `async`, como en p5.js v2, entonces 
se retornan promesas (para que puedan ser operadas con `await` o `Promise.all`).

El diseño interno de q5 permite que esto se pueda modificar dinámicamente durante la ejecución del sketch. 

**Parámetros**
- `bandera` <boolean> (opcional) - Indica si las funciones `load*` deben devolver promesas o no. Por defecto es `true`.



## Q5(scope, parent)
Q5(ambito, contenedor)

Funcion constructora. Crea una instancia de Q5.
