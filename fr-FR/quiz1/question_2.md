
--- question ---

---
legend: Question 2 sur 3
---

Ce bloc de code montre un bloc de boucle `chaque 500 ms`.

Qu'est-ce qu'une boucle ?

```microbit
loops.everyInterval(500, function () {
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("niveau sonore", input.soundLevel()))
})
```

--- choices ---

- (x) Une séquence d’instructions qui est répétée constamment ou jusqu’à ce qu’une certaine condition soit remplie.

  --- feedback ---

Bravo ! Les boucles sont un concept utilisé dans tous les langages de programmation. Les boucles se répètent constamment ou jusqu'à ce qu'une condition soit remplie.

  --- /feedback ---

- ( ) Une condition qui contrôle ce qui se passe dans un bloc logique.

  --- feedback ---

  Pas tout à fait. Une condition peut être utilisée pour comparer une valeur de variable avec autre chose. La condition ne boucle pas.

  --- /feedback ---

- ( ) Une séquence d'instructions qui exécute une tâche spécifique.

  --- feedback ---

  Pas tout à fait. Une séquence d'instructions pour une tâche spécifique est appelée une `fonction`.

  --- /feedback ---

--- /choices ---

--- /question ---
