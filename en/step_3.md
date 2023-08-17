## Sound the alarm

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
In this step you will add an alarm that triggers when the levels get too high. To stop the alarm adding to the noise you will make sure it only goes off once and can be reset whenever you want. 
</div>
<div>
Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png){:width="300px"}
</div>
</div>

### Set the maximum

You will need to make a Variable to set the sound level that will trigger the alarm.

--- task ---

Open the <code style="background-color: #dc143c">Variables</code> menu and click `Make a Variable`.

<img src="images/variable-menu.png" alt="The Variables block menu, open with the 'Make a variable' button highlighted" width="300"/>

--- /task ---

--- task ---

Name your new variable `maximum`. 

<img src="images/max-variable-name.png" alt="The 'New variable name' window, with the name 'maximum' written in the box" width="300"/>

--- /task ---

--- task ---

From the <code style="background-color: #dc143c">Variables</code> menu, grab the <code style="background-color: #dc143c">set maximum</code> block. 

<img src="images/set-max-start.png" alt="The Variables menu with the 'set maximum to 0' block highlighted" width="300"/>

Place the block inside the <code style="background-color: #1e90ff">on start</code> block, and change the `0` to `150`.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_D7PUcJXFR51p" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

`150` is a little over half the maximum sound level the micro:bit can sense, so that should be a good level to start with. 

### Turn the alarm off

You will also want to make sure the alarm noise itself does not add to the already noisy surroundings!

To do this you will use another variable that will be set to `false` when the alarm has not sounded, and then `true` when the alarm sounds. 

--- task ---

Create another new <code style="background-color: #dc143c">Variable</code> this time called `alarm`. 

<img src="images/alarm-variable-name.png" alt="The 'New variable name' window, with the name 'maximum' written in the box" width="300"/>

--- /task ---

--- task ---

Drag another <code style="background-color: #dc143c">set</code> block from the <code style="background-color: #dc143c">Variables</code> menu.

Place it inside the <code style="background-color: #1e90ff">on start</code> block. Underneath the previous one. 

--- /task ---

You need to set this new variable to `false` instead of a number.

--- task ---

Open the <code style="background-color: #00a4a6">Logic</code> menu. Grab a <code style="background-color: #00a4a6">false</code> block. 

<img src="images/false-block-location.png" alt="The bottom part of the Logic menu, showing the location of the false block in the 'Boolean' section" width="200"/>

Place this block over the top of the `0`. 

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_43jPJYC2z2fR" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

### Check if the alarm should sound

The alarm should only sound **if** the current sound level is **larger** than the maximum **and** the alarm variable is set to false. 

--- task ---

From the <code style="background-color: #00a4a6">Logic</code> menu grab an <code style="background-color: #00a4a6">if</code> block. 

<img src="images/if-block-location.png" alt="The Logic menu, open with an if block highlighted" width="300"/>

Place the block inside the <code style="background-color: #1e90ff">forever</code> underneath the <code style="background-color: #5c2d91">plot bar graph</code> block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_Fwg1j1V0qX3z" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

Open the <code style="background-color: #00a4a6">Logic</code> menu again and take an <code style="background-color: #00a4a6">and</code> block. 

<img src="images/and-block-location.png" alt="The bottom part of the Logic menu, showing the location of the and block in the 'Boolean' section" width="200"/>

Place it in the `true` section of the <code style="background-color: #00a4a6">if</code> block. 

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:75%;height:75%;" src="https://makecode.microbit.org/---codeembed#pub:_csx9JCEgUi7R" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

Now you need to add the **two** conditions either side of the **and**. 

This will mean that the code inside your <code style="background-color: #00a4a6">if</code> block will only run if **both** conditions are true. 

--- task ---

Again in the <code style="background-color: #00a4a6">Logic</code> menu, grab a <code style="background-color: #00a4a6">0 < 0</code>. 

Place it on one side of the <code style="background-color: #00a4a6">and</code> block. 



--- /task ---