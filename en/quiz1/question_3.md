
--- question ---

---
legend: Question 3 of 3
---
Here is the code for programming the `on button A pressed` and `on button B pressed` blocks.

```microbit
let level = 0
let maximum = 0
input.onButtonPressed(Button.A, function () {
    level += -1
    maximum += -50
    if (level < 1) {
        level = 5
        maximum = 250
    }
    basic.showNumber(level)
    basic.pause(500)
})
input.onButtonPressed(Button.B, function () {
    level += 1
    maximum += 50
    if (level < 5) {
        level = 5
        maximum = 250
    }
    basic.showNumber(level)
    basic.pause(500)
})
```

What will happen when the `B` button is pressed on the micro:bit?

--- choices ---

- ( ) The sound level will be changed by -1 and sensitivity by -50.


  --- feedback ---

  Not quite! Pressing button `A` will make these changes, but not button `B`.

  --- /feedback ---

- ( ) The sound level will be changed by 5 and sensitivity by -50.

  --- feedback ---

  Not quite! Neither button A or button B are programmed to change the sound level or sensitivity by these amounts.

  --- /feedback ---

- (x) The sound level will be changed by 1 and sensitivity by 50.

  --- feedback ---

  Awesome job! Button B has been programmed to increase the sound level by 1 and the sensitivity by 50.

  --- /feedback ---

--- /choices ---

--- /question ---
