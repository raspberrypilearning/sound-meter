\--- question ---

---

## legend: 質問3/3

以下は、「ボタンAが押されたとき」と「ボタンBが押されたとき」のブロックをプログラミングするためのコードです。

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

micro:bitの「B」ボタンを押すと、何が起こるでしょうか？

\--- choices ---

- ( )音量は‐1ずつ、感度は‐50ずつに変更されます。

  \--- feedback ---

  不正解！ ボタン「A」を押すとこれらの変更が実行されますが、ボタン「B」では実行されません。

  \--- /feedback ---

- ( ) 音量は5ずつ、感度は‐50ずつに変更されます。

  \--- feedback ---

  不正解！ ボタンAとボタンBはどちらとも、音の大きさや感度をこれだけの値分だけ変更するようにはプログラムされていません。

  \--- /feedback ---

- (x) 音量が1ずつ、感度が50ずつ変更されます。

  \--- feedback ---

  大正解です！ ボタンBは、音量を1ずつ、感度を50ずつ上げるようにプログラムされています。

  \--- /feedback ---

\--- /choices ---

\--- /question ---
