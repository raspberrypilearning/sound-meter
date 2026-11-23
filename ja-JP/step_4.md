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

前のステップでは、「上限」{:class='microbitvariables'} と 「アラーム」{:class='microbitvariables'} という 二つの変数を作成しました。

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

ブロック内の変数名をクリックして、「レベル」から「上限」に変更します。

「1」を「-50」に変更します。

<img src="images/change-variable.gif" alt="Animation showing the drop-down menu on the `change maximum by 1` variable block." width="300"/>

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

「論理」{:class='microbitlogic'} メニューから 「もし～なら」{:class='microbitlogic'} ブロックを取得します。

それを 「変数 上限 を -50 だけ増やす」{:class='microbitvariables'} ブロックの下に配置します。

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

「論理」{:class='microbitlogic'} メニューから、比較演算子の「0 < 0」{:class='microbitlogic'} を取得します。

それを「もし～なら」{:class='microbitlogic'} ブロック内の「真」スペース内に配置します。

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

「変数」{:class='microbitvariables'} メニューから、「レベル」{:class='microbitvariables'} ブロックを取得します。

それを 比較演算子の「0 < 0」{:class='microbitlogic'} ブロックの一つ目の 「0」 の中に配置します。

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

比較演算子の「0 < 0」{:class='microbitlogic'} ブロックの右側の「0」を「1」に変更します。

\--- /task ---

\--- task ---

「変数」{:class='microbitvariables'} メニューから、「変数を 0 にする」{:class='microbitvariables'} ブロックを取得します。

それを「もし～なら」{:class='microbitlogic'} ブロックの中に配置します。 選択された変数が 「レベル」{:class='microbitvariables'} であることを確認してください。

「変数を 0 にする」{:class='microbitvariables'} ブロックの 「0」 を 「5\`に変更します。

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

再び「変数」{:class='microbitvariables'} メニューから、別の「設定」{:class='microbitvariables'}ブロックをドラッグします。

それを「変数 レベル を 5 にする」{:class='microbitvariables'} ブロックの下に配置します。

変数名を 上限 に変更し、「0」を「250」に変更します。

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

「基本」{:class='microbitbasic'} メニューから、「数を表示」{:class='microbitbasic'} ブロックを取得します。

それを「もし～なら」{:class='microbitlogic'} ブロックの **下**（外側） に配置します。

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

「変数」{:class='microbitvariables'} メニューから、「レベル」{:class='microbitvariables'} ブロックを取得します。

それを「数を表示」{:class='microbitbasic'} ブロックの 「0」に配置します。

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

同じく「基本」{:class='microbitbasic'}メニューから、「一時停止（ミリ秒）」{:class='microbitbasic'}ブロックを取得します。

それを「数を表示」{:class='microbitbasic'} ブロックの下に配置します。

「100」を「500」に変更します。

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

### 最大音量を上げる

これで「ボタンAが押されたとき」{:class='microbitinput'} のプログラミングが完了しました。

次は、最大音量を上げて感度を下げるために、「ボタンBが押されたとき」{:class='microbitinput'}のコードを同じように作ります。

\--- task ---

配置した「ボタンAが押されたとき」{:class='microbitinput'} ブロックの枠全体を右クリックし、 **複製する** をクリックします。

![「ボタンAが押されたとき」ブロックを右クリックし、メニューから「複製する」が強調されているアニメーション。](images/onbuttonA-duplicate.gif)

コードエディタ上に、二つの「ボタンAが押されたとき」{:class='microbitinput'} ブロックが 並びます。

\--- /task ---

\--- task ---

複製された「ボタンAが押されたとき」{:class='microbitinput'}ブロックの「A」をクリックします。 ドロップダウンメニューが開きます。

「A」を「B」に変更します。

<img src="images/button-menu.png" alt="The drop-down menu for 'on button A pressed' that lets you change the block to button B." width="400"/>

\--- /task ---

\--- task ---

「ボタンBが押されたとき」{:class='microbitinput'} ブロックの中身を：

- 「変数 レベル を変える」{:class='microbitvariables'} ブロックの 「-1」 を 「1」 にする

- 「変数 上限 を変える」{:class='microbitvariables'} ブロック内の 「-50」 を 「50」 にする

<img src="images/onbuttonB-changes.png" alt="The `on button B pressed` block with the change level and change maximum variables shown." width="350"/>

\--- /task ---

\--- task ---

「もし〜なら」{:class='microbitlogic'} ブロックの条件式を：

- 不等号の「<」を「>」に変更する
- 数字の「1」を「5」に変更する

「もし〜なら」{:class='microbitlogic'} ブロックの条件式を：

- 「変数 レベル を 5 にする」{:class='microbitvariables'} ブロック内の 「5」 を 「1」 に変更する
- 「変数 上限 を 50 にする」{:class='microbitvariables'} ブロック内の 「250」 を 「50」 に変更する

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

### 通常の音量レベルを設定する

プログラムが起動したときに、ちょうどよい通常の感度レベルからスタートするように「最初だけ」{:class='microbitbasic'} にコードを追加します。

\--- task ---

「変数」{:class='microbitvariables'} メニューから、「変数 上限を 0 にする」{:class='microbitvariables'} ブロックを取得します。

それを「最初だけ」{:class='microbitbasic'} ブロックの中に配置します。

\--- /task ---

\--- task ---

変数名をクリックして 「上限」 から「レベル」に変更します。

「変数 レベル を 0 にする」{:class='microbitvariables'} ブロック内の 「0」 を 「3」 に変更します。

```microbit
let maximum = 150
let alarm = false
let level = 3
```

\--- /task ---

\--- task ---

**プログラムのテスト方法**

- AボタンとBボタンを押して、画面に表示される感度レベルが上がったり下がったりすることを確認します

起動時の初期状態はレベル3です。

シミュレーターのマイクの入力レベル（音量バー）を上下に **動かして** 、それぞれのレベル（1〜5）ごとにアラームが鳴る最大音量が変化することを確認してください。

\--- /task ---

\--- task ---

完成したプログラムをmicro:bitにダウンロードしましょう！

\--- /task ---

[[[download-to-microbit]]]

よくできました！ これで、完全に動作する音量計 または 光度計が、完成しました！

次へ進んで、これまでに学んだ内容をクイズで確かめてみましょう！
