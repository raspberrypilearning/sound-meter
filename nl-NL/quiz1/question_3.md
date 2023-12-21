
--- question ---

---
legend: Vraag 3 van 3
---
Hier is de code voor het programmeren van de `wanneer knop A wordt ingedrukt` en `wanneer knop B wordt ingedrukt` blokken.

```microbit
let niveau = 0
let maximum = 0
input.onButtonPressed(Button.A, function () {
    niveau += -1
    maximum += -50
    if (niveau < 1) {
        niveau = 5
        maximum = 250
    }
    basic.showNumber(niveau)
    basic.pause(500)
})
input.onButtonPressed(Button.B, function () {
    niveau += 1
    maximum += 50
    if (niveau < 5) {
        niveau = 5
        maximum = 250
    }
    basic.showNumber(niveau)
    basic.pause(500)
})
```

Wat gebeurt er als de `B` knop op de micro:bit wordt ingedrukt?

--- choices ---

- ( ) Het geluidsniveau wordt gewijzigd met -1 en de gevoeligheid met -50.


  --- feedback ---

  Niet helemaal! Als je op knop `A` drukt, worden deze wijzigingen doorgevoerd, maar niet op knop `B`.

  --- /feedback ---

- ( ) Het geluidsniveau wordt gewijzigd met -5 en de gevoeligheid met -50.

  --- feedback ---

  Niet helemaal! Noch knop A, noch knop B zijn geprogrammeerd om het geluidsniveau of de gevoeligheid met deze hoeveelheden te wijzigen.

  --- /feedback ---

- (x) Het geluidsniveau zal worden gewijzigd met 1 en gevoeligheid met 50.

  --- feedback ---

  Goed gedaan! Knop B is geprogrammeerd om het geluidsniveau met 1 en de gevoeligheid met 50 te verhogen.

  --- /feedback ---

--- /choices ---

--- /question ---
