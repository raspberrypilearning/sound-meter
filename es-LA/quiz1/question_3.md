
--- question ---

---
legend: Pregunta 3 de 3
---
Aqui esta el codigo para programar los bloques `al presionar el boton A` y `al presionar el boton B`.

```microbit
let nivel = 0
let maximo = 0
input.onButtonPressed(Button.A, function () {
    nivel += -1
    maximo += -50
    if (nivel < 1) {
        nivel = 5
        maximo = 250
    }
    basic.showNumber(nivel)
    basic.pause(500)
})
input.onButtonPressed(Button.B, function () {
    nivel += 1
    maximo += 50
    if (nivel < 5) {
        nivel = 5
        maximo = 250
    }
    basic.showNumber(nivel)
    basic.pause(500)
})
```

¿Que pasara cuando el boton `B` sea presionado en el micro:bit?

--- choices ---

- ( ) El nivel de sonido cambiara en -1 y la sensibilidad en -50.


  --- feedback ---

  ¡No exactamente! Presionando el boton `A` realizara estos cambios, no al presionar el boton `B`.

  --- /feedback ---

- ( ) El nivel de sonido se modificara en 5 y la sensibilidad en -50.

  --- feedback ---

  ¡No exactamente! Ni el boton A o B estan programados para cambiar el nivel de sonido o sensibilidad en estas cantidades.

  --- /feedback ---

- (x) El nivel de sonido cambiara en 1 y la sensibilidad en 50.

  --- feedback ---

  ¡Gran trabajo! El boton B ha sido programado para incrementar el nivel de sonido en 1 y la sensibilidad en 50.

  --- /feedback ---

--- /choices ---

--- /question ---
