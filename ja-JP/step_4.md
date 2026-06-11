## 感度を変える

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

このステップでは、micro:bitのボタンをプログラミングして、アラームの感度を1（最も感度が低い）から5（最も感度が高い）までで調整できるようにします。

</div>
<div>

![AボタンとBボタンをクリックしたときに音量のレベル数値がLED画面に表示されるmicro:bitシミュレーター。 Aボタンでレベルが下がり、Bボタンでレベルが上がります。](images/buttons-pressed-demo.gif){:width="300px"}

</div>
</div>

### 上限値を下げる

Aボタンは左側にあるので、これを使ってアラームの上限値を下げる処理を作ります。

\--- task ---

「入力」{:class='microbitinput'} メニューから 「ボタンAが押されたとき」{:class='microbitinput'} ブロックを取得してコードエディタに配置します。

<img src="images/on-button-location.png" alt="The Input menu with the 'on button A pressed' block highlighted at the top." width="300"/>

\--- /task ---

前のステップでは、「上限値」{:class='microbitvariables'} と 「アラーム」{:class='microbitvariables'} という 2 つの変数を作成しました。

ここでは、現在の感度の段階を管理するために、もう一つ **level** という変数を作成します。

\--- task ---

「変数」{:class='microbitvariables'}メニューから、\*\*変数を追加する...\*\*をクリックして、「レベル」という名前の変数を作成します。

\--- /task ---

\--- task ---

変数メニューから「変数を 1 ずつ変える」{:class='microbitvariables'} ブロックを取得して、「ボタンAが押されたとき」{:class='microbitinput'} ブロックの中に配置します。

「1」を「-1」に変更します。

```microbit
let level = 0
input.onButtonPressed(Button.A, function () {
    level += -1
})
```

\--- /task ---

\--- task ---

「変数」{:class='microbitvariables'} メニューから、もう一つ「変数を 1 ずつ変える」{:class='microbitvariables'} ブロックを取得します。

それを先ほどの「変数を -1 ずつ変える」{:class='microbitvariables'} ブロックの**下**に配置します。

ブロック内の変数名をクリックして、「レベル」から「上限値」に変更します。

「1」を「-50」に変更します。

<0/>

```microbit
let level = 0
let maximum = 0
input.onButtonPressed(Button.A, function () {
    level += -1
    maximum += -50
})
```

\--- /task ---

これにより、Aボタンを押すたびに感度レベルが1ずつ減り、音量の上限値が50ずつ下がります。

もしレベルがすでに「1」の状態でAボタンが押された場合は、レベルが「0」になるのではなく「5」に切り替わるようにする必要があります。

\--- task ---

From the `Logic`{:class='microbitlogic'} menu, drag an `if`{:class='microbitlogic'} block.

Place it below the `change maximum by -50`{:class='microbitvariables'} block.

```microbit
let level = 0
let maximum = 0
input.onButtonPressed(Button.A, function () {
    level += -1
    maximum += -50
    if (true) {
    	
    }
})
```

\--- /task ---

\--- task ---

From the `Logic`{:class='microbitlogic'} menu, drag the `0 < 0`{:class='microbitlogic'} comparison block.

Place it inside the `true` space in the `if`{:class='microbitlogic'} block.

```microbit
let level = 0
let maximum = 0
input.onButtonPressed(Button.A, function () {
    level += -1
    maximum += -50
    if (0 < 0) {
    	
    }
})
```

\--- /task ---

\--- task ---

From the `Variables`{:class='microbitvariables'} menu, drag the `level`{:class='microbitvariables'} block.

Place it inside the first `0` of the `0 < 0`{:class='microbitlogic'} comparison block.

```microbit
let level = 0
let maximum = 0
input.onButtonPressed(Button.A, function () {
    level += -1
    maximum += -50
    if (level < 0) {
    	
    }
})
```

\--- /task ---

\--- task ---

Change the `0` to `1` on the right-hand side of the `0 < 0`{:class='microbitlogic'} comparison block.

\--- /task ---

\--- task ---

From the `Variables`{:class='microbitvariables'} menu, drag the `set`{:class='microbitvariables'} block.

Place it inside the `if`{:class='microbitlogic'} block. Ensure the variable selected is `level`{:class='microbitvariables'}.

Change the `0` to `5` on the `set level to 0`{:class='microbitvariables'} block.

```microbit
let level = 0
let maximum = 0
input.onButtonPressed(Button.A, function () {
    level += -1
    maximum += -50
    if (level < 1) {
        level = 5
    }
})
```

\--- /task ---

\--- task ---

Again from the `Variables`{:class='microbitvariables'} menu, drag another `set`{:class='microbitvariables'} block.

Place it below the `set level to 5`{:class='microbitvariables'} block.

Change the `0` to `250`.

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
})
```

\--- /task ---

\--- task ---

From the `Basic`{:class='microbitbasic'} menu, drag the `show number`{:class='microbitbasic'} block.

Place it **below** the `if`{:class='microbitlogic'} block.

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
    basic.showNumber(0)
})
```

\--- /task ---

\--- task ---

From the `Variables`{:class='microbitvariables'} menu, drag the `level`{:class='microbitvariables'} block.

Place it in the `0` in the `show number`{:class='microbitbasic'} block.

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
})
```

\--- /task ---

\--- task ---

Also from the `Basic`{:class='microbitbasic'} menu, drag the `pause`{:class='microbitbasic'} block.

Place it below the `show number`{:class='microbitbasic'} block.

Change the `100` to `500`.

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
```

\--- /task ---

### Increase the maximum sound level

You have now programmed the `on button A pressed`{:class='microbitinput'} block.

You will need to do the same for `on button B pressed`{:class='microbitinput'} to increase the maximum.

\--- task ---

Right-click on the entire `on button A pressed`{:class='microbitinput'} block and click **Duplicate**.

![Animation showing the right-click menu on the 'on button A pressed' block with 'Duplicate' highlighted.](images/onbuttonA-duplicate.gif)

There will now be two `on button A pressed`{:class='microbitinput'} blocks in the code editor panel.

\--- /task ---

\--- task ---

Click on the `A` in the duplicated `on button A pressed`{:class='microbitinput'} block. A drop-down menu will open.

Change the `A` to `B`.

<img src="images/button-menu.png" alt="The drop-down menu for 'on button A pressed' that lets you change the block to button B." width="400"/>

\--- /task ---

\--- task ---

Inside the `on button B pressed`{:class='microbitinput'} block:

- Change the `-1` to `1` in the `change level`{:class='microbitvariables'} block

- Change the `-50` to `50` in the `change maximum`{:class='microbitvariables'} block

<img src="images/onbuttonB-changes.png" alt="The `on button B pressed` block with the change level and change maximum variables shown." width="350"/>

\--- /task ---

\--- task ---

For the `if`{:class='microbitlogic'} block's conditions:

- Change the `<` to a `>`
- Change the `1` to `5`

Inside the `if`{:class='microbitlogic'} block:

- Change the `5` to `1` in the `set level to 5`{:class='microbitvariables'} block
- Change the `250` to `50` in the `set maximum to 50`{:class='microbitvariables'} block

```microbit
let level = 0
let maximum = 0
input.onButtonPressed(Button.B, function () {
    level += 1
    maximum += 50
    if (level > 5) {
        level = 1
        maximum = 50
    }
    basic.showNumber(level)
    basic.pause(500)
})
```

\--- /task ---

### Set a normal sound level

You need to program a normal alarm sensitivity level by using the `on start`{:class='microbitbasic'} block.

\--- task ---

From the `Variables`{:class='microbitvariables'} menu, drag a `set maximum to 0`{:class='microbitvariables'} block.

Place it inside the `on start`{:class='microbitbasic'} block.

\--- /task ---

\--- task ---

Click on the variable name `maximum` and change it to `level`.

Change the `0` to `3` in the `set level`{:class='microbitvariables'} block.

```microbit
let maximum = 150
let alarm = false
let level = 3
```

\--- /task ---

\--- task ---

**Test your program**

- Press the A and B buttons to see the sound levels increase and decrease

The default starting point is level 3.

**Drag** the mic input levels up and down to test the maximum sound for each level when using the simulator.

\--- /task ---

\--- task ---

Download your program onto your micro:bit!

\--- /task ---

[[[download-to-microbit]]]

Well done! You now have a fully working sound or light meter!

Next, it is time to check what you have learnt!
