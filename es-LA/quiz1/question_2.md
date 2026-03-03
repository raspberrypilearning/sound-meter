
--- question ---

---
legend: Pregunta 2 de 3
---

Este bloque de código muestra un bloque de bucle `cada 500 ms`.

¿Que es un loop?

```microbit
loops.everyInterval(500, function () {
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("Nivel de sonido", input.soundLevel()))
})
```

--- choices ---

- (x) Una secuencia de instrucciones que se repiten hasta que se cumple cierta condicion.

  --- feedback ---

¡Gran trabajo! Los bucles son un concepto usado en todos los lenguajes de programacion. Los bucles se repiten hasta que se cumple cierta condicion.

  --- /feedback ---

- ( ) Una condicion controla lo que sucede en un bloque de logica.

  --- feedback ---

  No exactamente. Una condicion puede ser usada para comparar el valor de una variable con otra cosa. Una condicion no es un bucle.

  --- /feedback ---

- ( ) Una secuencia de instrucciones que llevan a cabo una tarea especifica.

  --- feedback ---

  No exactamente. Se le llama `funcion` a una secuencia de intrucciones para una tarea especifica.

  --- /feedback ---

--- /choices ---

--- /question ---
