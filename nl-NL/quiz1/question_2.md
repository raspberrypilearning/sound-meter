
--- question ---

---
legend: Vraag 2 van 3
---

Dit codeblok toont een `elke 500 ms` lusblok.

Wat is een lus?

```microbit
loops.everyInterval(500, function () {
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("Sound level", input.soundLevel()))
})
```

--- choices ---

- (x) Een reeks instructies die constant wordt herhaald of totdat een bepaalde voorwaarde is bereikt.

  --- feedback ---

Goed gedaan! Lussen zijn een concept dat in alle programmeertalen wordt gebruikt. Lussen herhalen constant of totdat een voorwaarde is bereikt.

  --- /feedback ---

- ( ) Een voorwaarde die bepaalt wat er in een logisch blok gebeurt.

  --- feedback ---

  Niet helemaal. Een voorwaarde kan worden gebruikt om een variabele waarde met iets anders te vergelijken. De voorwaarde herhaalt niet.

  --- /feedback ---

- ( ) Een reeks van instructies die een specifieke taak uitvoert.

  --- feedback ---

  Niet helemaal. Een reeks instructies voor een specifieke taak heet een `functie`.

  --- /feedback ---

--- /choices ---

--- /question ---
