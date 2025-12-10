
--- question ---

---
legend: 質問2/3
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

  不正解です。 条件は、変数の値を他の値と比較するために使用できます。 The condition does not loop.

  --- /feedback ---

- ( ) A sequence of instructions that performs a specific task.

  --- feedback ---

  不正解です。 A sequence of instructions for a specific task is called a `function`.

  --- /feedback ---

--- /choices ---

--- /question ---
