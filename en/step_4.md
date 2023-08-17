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

--- /task ---

In the previous step you created two variables, `maximum` and `alarm`. You will need to create another.

--- task ---

In the <code style="background-color: #DC143C">Variables</code> menu, click on `make a variable` to create a variable called `level`.

--- /task --- 

--- task ---

Drag the `change level by 1` block and place it inside the `on button A pressed` block.

Change the `1` to `-1`.

--- /task ---

--- task ---

From the <code style="background-color: #DC143C">Variables</code> menu, also drag the `change maximum by 1` block. 

Place it below the `change level by -1` block.

Change the `1` to `-50`

--- /task ---

This means every time you press the button A, it will decrease the sound level by 1 and reduce the sound sensitivity by 50 decibels.

What happens if the sound levels drop below 1 to -1? You want to stop this from happening.

--- task ---


--- /task ---

--- task ---

Step content... 
Can use:
**Test:**
**Choose:**
**Tip:**

--- /task ---

--- save ---