
--- question ---

---
legend: Question 3 sur 3
---
Voici le code pour programmer les blocs `lorsque le bouton A est pressé` et `lorsque le bouton B est pressé`.

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

Que se passera-t-il lorsque le bouton `B` sera pressé sur le micro:bit ?

--- choices ---

- ( ) Le niveau sonore sera modifié de -1 et la sensibilité de -50.


  --- feedback ---

  Pas tout à fait ! Appuyer sur le bouton `A` effectuera ces modifications, mais pas sur le bouton `B`.

  --- /feedback ---

- ( ) Le niveau sonore sera modifié de 5 et la sensibilité de -50.

  --- feedback ---

  Pas tout à fait ! Ni le bouton A ni le bouton B ne sont programmés pour modifier le niveau sonore ou la sensibilité de ces quantités.

  --- /feedback ---

- (x) Le niveau sonore sera modifié de 1 et la sensibilité de 50.

  --- feedback ---

  Super ! Le bouton B a été programmé pour augmenter le niveau sonore de 1 et la sensibilité de 50.

  --- /feedback ---

--- /choices ---

--- /question ---
