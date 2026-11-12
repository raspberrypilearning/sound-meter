\--- question ---

---

## legend: 質問2/3

このプログラミングコードは、500ミリ秒ごとに実行されるループブロックを示しています。

ループとは何でしょう？

```microbit
loops.everyInterval(500, function () {
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
    datalogger.log(datalogger.createCV("Sound level", input.soundLevel()))
})
```

\--- choices ---

- （x）一定の条件に達するまで、または継続的に繰り返される一連の命令。

  \--- feedback ---

大正解です！ ループは、あらゆるプログラミング言語で用いられる考え方です。 ループは、条件が満たされるまで、または常に繰り返されます。

\--- /feedback ---

- ( ) 論理ブロック内で何が起こるかを決める条件。

  \--- feedback ---

  不正解。 条件を使うと、変数に入っている値を別の値と比べることができます。 この条件はループしません。

  \--- /feedback ---

- ( ) 特定のタスクを実行する一連の命令。

  \--- feedback ---

  不正解。 関数とは、特定の作業を行うためにまとめられた命令の集まりです。

  \--- /feedback ---

\--- /choices ---

\--- /question ---
