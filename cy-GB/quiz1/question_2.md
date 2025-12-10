
--- question ---

---
legend: Cwestiwn 2 o 3
---

This block of code shows a `every 500 ms` loop block.

What is a loop?

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

- (x) A sequence of instructions that is repeated constantly or until a certain condition is reached.

  --- feedback ---

Fantastic work! Loops are a concept used across all programming languages. Loops repeat constantly or until a condition is reached.

  --- /feedback ---

- ( ) A condition that controls what happens in a logic block.

  --- feedback ---

  Ddim cweit. A condition can be used to compare a variable value with something else. The condition does not loop.

  --- /feedback ---

- ( ) A sequence of instructions that performs a specific task.

  --- feedback ---

  Ddim cweit. A sequence of instructions for a specific task is called a `function`.

  --- /feedback ---

--- /choices ---

--- /question ---
