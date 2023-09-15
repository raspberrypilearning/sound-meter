## Sound the alarm

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step, you will add an alarm that triggers when the sound level get too high. To stop the alarm adding to the noise, you will make sure it only goes off once and can be reset whenever you want. 
</div>
<div>

![The code to trigger the alarm. Inside an 'every 500 ms' block, the sound level is plotted on the LEDs. Afterwards, an if statement is used to check if the sound level exceeds the maximum and whether the alarm variable is set to false. Inside the if block, a sound is played and the alarm variable is set to 'true'.](images/alarm-code-demo.png){:width="300px"}

</div>
</div>

### Set the maximum

You will need to make a variable to hold the sound level that will trigger the alarm.

--- task ---

Open the <code style="background-color: #dc143c">Variables</code> menu and click **Make a Variable**.

<img src="images/variable-menu.png" alt="The Variables block menu with the 'Make a Variable' button highlighted." width="350"/>

--- /task ---

--- task ---

Name your new variable `maximum`. 

<img src="images/max-variable-name.png" alt="The 'New variable name' window with the name 'maximum' written in the box." width="400"/>

--- /task ---

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, get the <code style="background-color: #dc143c">set maximum</code> block. 

<img src="images/set-max-start.png" alt="The Variables menu with the 'set maximum to 0' block highlighted." width="350"/>

Place the block inside the <code style="background-color: #1e90ff">on start</code> block, and change the `0` to `150`.

<div style="position:relative;height:calc(125px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_D7PUcJXFR51p" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

THe value `150` is a little more than half the maximum sound level the micro:bit can sense, so that should be a good level to start with. 

--- collapse ---

---
title: For micro:bit V1
---

This maximum value works for light levels, too!

--- /collapse ---

### Turn the alarm off

You also want to make sure the alarm noise does not add to the already noisy environment!

To do this, you will use another variable that will be set to `false` to start, and it will change to `true` when the alarm sounds. 

--- task ---

Create another new <code style="background-color: #dc143c">Variable</code>, this time called `alarm`.

<img src="images/alarm-variable-name.png" alt="The 'New variable name' window with the name 'alarm' written in the box." width="350"/>

--- /task ---

--- task ---

Drag the <code style="background-color: #dc143c">set alarm</code> block from the <code style="background-color: #dc143c">Variables</code> menu.

Place it inside the <code style="background-color: #1e90ff">on start</code> block. 

--- /task ---

You need to set this new variable to `false` instead of a number.

--- task ---

Open the <code style="background-color: #00a4a6">Logic</code> menu. 

Grab a <code style="background-color: #00a4a6">false</code> block. 

<img src="images/false-block-location.png" alt="The bottom part of the Logic menu, showing the location of the false block in the 'Boolean' section." width="200"/>

Place this block over the top of the `0`. 

<div style="position:relative;height:calc(225px + 5em);width:100%;overflow:hidden;"><iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_Pc7HtrCL7KeK" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

### Check if the alarm should sound

The alarm should only sound **if:** 

+ The sound level is **larger** than the maximum   
**AND** 
+ The alarm variable is **equal to** `false` 

--- task ---

From the <code style="background-color: #00a4a6">Logic</code> menu, get an <code style="background-color: #00a4a6">if</code> block. 

<img src="images/if-block-location.png" alt="The Logic menu with an 'if' block highlighted." width="350"/>

Place the block inside the <code style="background-color: #00aa00">every</code> loop underneath the <code style="background-color: #378273">log data</code> block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_Ve9W13cyKXTi" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

Open the <code style="background-color: #00a4a6">Logic</code> menu again and take an <code style="background-color: #00a4a6">and</code> block. 

<img src="images/and-block-location.png" alt="The bottom part of the Logic menu, showing the location of the 'and' block in the 'Boolean' section." width="200"/>

Place it in the `true` section of the <code style="background-color: #00a4a6">if</code> block. 

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_JYu2mx9ku6pC" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

Now you need to add the **two** conditions either side of the **and**. 

--- task ---

Again in the <code style="background-color: #00a4a6">Logic</code> menu, get a <code style="background-color: #00a4a6">0 < 0</code> condition block. 

Place it on one side of the <code style="background-color: #00a4a6">and</code> block. 

Use the drop-down menu to change the less than symbol (`<`) to a greater than (`>`) symbol. 

![A demo of clicking the drop-down menu and changing the less than symbol to a greater than symbol in the condition.](images/changing-condition.gif)

--- /task ---

--- task ---

From the <code style="background-color: #d400d4">Input</code> menu, drag a <code style="background-color: #d400d4">sound level</code> block.

Put it in the first `0` of the <code style="background-color: #00a4a6">0 > 0</code> block

From the <code style="background-color: #dc143c">Variables</code> menu, drag a <code style="background-color: #dc143c">maximum</code> block.

Put it in the second `0` of the <code style="background-color: #00a4a6">0 > 0</code> block.

Your code should look like this:

<div style="position:relative;height:calc(275px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_L7M4isPeYR3c" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- collapse ---

---
title: For micro:bit V1
---

From the <code style="background-color: #d400d4">Input</code> menu, drag a <code style="background-color: #d400d4">light level</code> block.

Put it in the first `0` of the <code style="background-color: #00a4a6">0 > 0</code> block.

From the <code style="background-color: #dc143c">Variables</code> menu, drag a <code style="background-color: #dc143c">maximum</code> block.

Put it in the second `0` of the <code style="background-color: #00a4a6">0 > 0</code> block.

Your code should look like this:

<div style="position:relative;height:calc(275px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_iCic5U99A508" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /collapse ---

--- /task ---

You only want to set the alarm off if the <code style="background-color: #dc143c">alarm</code> variable **is equal to** <code style="background-color: #00a4a6">false</code>. 

--- task ---

Get a <code style="background-color: #00a4a6">0 = 0</code> condition block from the <code style="background-color: #00a4a6">Logic</code> menu. 

Place it on the other side of the <code style="background-color: #00a4a6">and</code> block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_X84gwbPC3guw" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

Place an <code style="background-color: #dc143c">alarm</code> variable block on one side of the equal sign and a <code style="background-color: #00a4a6">false</code> block on the other side. Like this:

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_4sYXrcHcg0Lt" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

### Sound the alarm

Now it's time to add your alarm sound!

--- task ---

From the <code style="background-color: #e63022">Music</code> menu, take a <code style="background-color: #e63022">play</code> block. 

<img src="images/play-block-location-v2.png" alt="The 'micro:bit v2' section of the Music menu, with the 'play' block highlighted at the top of the section." width="250"/>

Place this inside the <code style="background-color: #00a4a6">if</code> block that checks if the alarm should sound. 

<div style="position:relative;height:calc(200px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_bHYiMdKDjcw2" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- collapse ---

---
title: For micro:bit V1
---

The micro:bit V1 has no speaker, so you have to adapt the program for the alarm. 

Rather than an alarm that uses sound, you can display an icon on the LEDs when the light level is higher than the maximum. 

From the <code style="background-color: #1e90ff">Basic</code> menu, get a <code style="background-color: #1e90ff">show icon</code> block.

Place this inside the <code style="background-color: #00a4a6">if</code> block that checks if the alarm should sound. 

**Select** an icon to use for your alarm. 

<div style="position:relative;height:calc(275px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_YCfaePdWAchL" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /collapse ---

--- /task ---

--- task ---

**Choose** which alarm sound you would like to use, from the available sounds in the drop-down menu. 

![The drop-down menu in the play block, which lets you choose which sound you would like to play.](images/choose-sound.gif)

--- /task ---

--- task ---

Inside your <code style="background-color: #1e90ff">on start</code> block, **right click** on the <code style="background-color: #dc143c">set</code> block and select **Duplicate**. 

![A demo of right clicking on the 'set alarm to false' block, and then duplicating it.](images/duplicate-block.gif)

Place the duplicated block below the <code style="background-color: #e63022">play</code> block. 

Change the <code style="background-color: #00a4a6">false</code> to <code style="background-color: #00a4a6">true</code>.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_UmibCbeCJhPm" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

### Reset the alarm

When the alarm goes off, you will want to reset it.

You can use the touch logo on the micro:bit to do this.

<img src="images/logo-location.png" alt="The microbit logo." width="200"/>

--- task ---

From the <code style="background-color: #d400d4">Input</code> menu, drag an <code style="background-color: #d400d4">on logo</code> block.

<img src="images/onlogo-block-location.png" alt="The logo on the top of the microbit above the LEDs." width="200"/>

From your <code style="background-color: #1e90ff">on start</code> block, duplicate the <code style="background-color: #dc143c">set alarm</code> block and place it inside the <code style="background-color: #d400d4">on logo</code> block.

<div style="position:relative;height:calc(150px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_2eDAPFTsAVxh" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- collapse ---

---
title: For micro:bit V1
---

There is no touch sensor in the logo on the micro:bit V1, so instead you can use both the `A` and `B` buttons.

From the <code style="background-color: #d400d4">Input</code> menu, drag an <code style="background-color: #d400d4">on button</code> block.

<img src="images/on-button-location.png" alt="The Input menu with the 'on button A' block highlighted." width="350"/>

Use the drop-down menu to change the button to <code style="background-color: #d400d4">A+B</code>.

From your <code style="background-color: #1e90ff">on start</code> block, duplicate the <code style="background-color: #dc143c">set alarm</code> block and place it inside the <code style="background-color: #d400d4">on button</code> block.     

<div style="position:relative;height:calc(150px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:100%;height:100%;" src="https://makecode.microbit.org/---codeembed#pub:_L6pHzMi2F4m0" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /collapse ---

--- /task ---

Next you are going to use the `A` button and `B` button to change the sensitivity of your alarm!
