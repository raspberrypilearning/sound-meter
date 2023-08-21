## Change the sensitivity

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">

In this step you will program the buttons on the micro:bit to be used to change the sound levels and adjust the sensitivity of the sound that could be considered too high for you. You will be able to increase and decrease the sound levels. You will be using a range of sound levels from 1-5.

</div>
<div>
Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png){:width="300px"}
</div>
</div>

### Decrease the sound level

You can complete this task by using the A and B buttons on the micro:bit

--- task ---

From the <code style="background-color: #D400D4">Input</code> menu, drag out an `on button A pressed` block and place it in the code editor.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_Cef96Ef0YiYx" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

In the previous step you created two variables, `maximum` and `alarm`. You will need to create another.

--- task ---

From the <code style="background-color: #DC143C">Variables</code> menu, click on `make a variable` to create a variable called `level`.

--- /task --- 

--- task ---

Drag the `change ... by 1` block and place it inside the `on button A pressed` block. 

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_hiaDED72s9q0" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

Change the variable shown on the block from `maxium` to `level` by clicking on the variable name.

![Animation showing the drop down menu on the `change maximum by 1` variable block](images/change-variable.gif)

Change the `1` to `-1`.

--- /task ---

--- task ---

From the <code style="background-color: #DC143C">Variables</code> menu, also drag the `change maximum by 1` block. 

Place it below the `change level by -1` block.

Change the `1` to `-50`

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_fz1FgF5aEi7k" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

This means every time you press the button A, it will decrease the sound level by 1 and reduce the sound sensitivity by 50 decibels.

What happens if the sound levels drop below 1 to 0? You want to stop this from happening using an `if` block.

--- task ---

From the <code style="background-color: #00A4A6">Logic</code> menu, drag out an `if..true..then` block. 

Place it below the `change maximum by -50` block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_5kbWwj8aHeTj" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

From the <code style="background-color: #00A4A6">Logic</code> menu, drag out the `0 < 0` comparison block.

Place it inside the `true` space in the `if..true..then` block. 

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_JrAM55EWFeEj" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

From the <code style="background-color: #DC143C">Variables</code> menu, drag out the `level` block.

Place it inside the `0` on the left hand side of the `0 < 0` comparison block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_2iFC25Dt3KRt" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

Change the `0` to `1` on the right hand side of the `0 < 0` comparison block.

--- /task ---

--- task ---

From the <code style="background-color: #DC143C">Variables</code> menu, drag out the `set maximum to 0` block.

Place it inside the `if.. then` block. Ensure you change the variable selected from `maximum` to `level`.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_Lvrdu09btA3i" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

Change the `0` to `5` on the `set level to 0` block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_L8uHrDTJ14mH" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

Also from the <code style="background-color: #DC143C">Variables</code> menu, drag out the `set maximum to 0` block.

Place it below the `set level to 5` block.

Change the `0` to `250` on the `set maximum to 0` block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_Pm3REheUD1uo" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

From the <code style="background-color: #1E90FF">Basic</code> menu, drag out the `show number 0` block.

Place it below the `if.. then` block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_ACcH4j7hj5p1" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

From the <code style="background-color: #DC143C">Variables</code> menu drag out the `level` block.

Place it in the `0` in the `show number 0` block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_KDyMygJveb02" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

Also from the <code style="background-color: #1E90FF">Basic</code> menu, drag out the `pause ms 100`block.

Place it below the `show number` block. Change the `100` to `500`.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_TE52mwevkU37" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

### Decrease the sound level

Now you have programmed the `on button A pressed` block, you will need to do the same for `on button B`.

--- task ---

Right-click on the entire `on button A pressed` block and click `Duplicate`.

![Animation showing the right-click menu on the 'on button A pressed' block with 'Duplicate highlighted](images/onbuttonA-duplicate.gif)

There will now be two `on button A pressed` block on the code editor panel.

--- /task ---

--- task ---

Click on the `A` on the duplicated `on button A pressed` block, a drop down menu will open.

![The drop down menu on button A to change the block to button B](images/button-menu.png)

Change the `A` to `B`. There should now be `on button A pressed` and `on button B pressed` blocks on the code editor panel.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_9Kagwi4L3Ppp" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

Change the `-1` to `1` on the `change level by -1` block inside the `on button B pressed` block.

Change the `-50` to `50` on the `change maximum by -50` block inside the `on button B pressed` block.

![The `on button B pressed` block with the change level and change maximum variables shown.](images/onbuttonB-changes.png)

--- /task ---

--- task ---

Change the `1` to `5` inside the second part of the `if.. then` block on the `on button B pressed` block.

--- /task ---

--- task ---

Change the `5` to `1` on the `set level to 5` block inside the `if level > 5` block.

Change the `250` to `50` on the `set maximum to 50` block inside the `if level > 5` block.

![The final blocks of code showing the changes made to `on button B pressed`.](images/onbuttonB-final.png)

--- /task ---

### Set a normal sound level

Using the `on start` block, you will need to program a normal sound level and the maximum sensitivity.

--- task ---

From the <code style="background-color: #DC143C">Variables</code> menu, drag out a `set maximum to 0` block.

Place it inside the `on start` block

Click on the variable name `maximum` and change it to `alarm`

--- /task ---

--- task ---

From the <code style="background-color: #00A4A6">Logic</code> menu, drag out a `false` block and place it inside the `0` on the `set alarm to 0` block.

--- /task ---

--- task ---

From the <code style="background-color: #DC143C">Variables</code> menu, drag out a `set maximum to 0` block.

Place it below the  `set alarm to false` block.

Click on the variable name `maximum` and change it to `level`

--- /task ---

--- task ---

Change the `0` to `3` on the `set level to 0` block.

--- /task ---

--- task ---

From the <code style="background-color: #DC143C">Variables</code> menu, drag out a `set maximum to 0` block.

Place it below the  `set level to 3` block.

--- /task ---


--- task ---

Step content... 
Can use:
**Test:**
**Choose:**
**Tip:**

--- /task ---

--- save ---