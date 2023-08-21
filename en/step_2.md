## Log the sound level

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
You are going to create your MakeCode project and add code to measure the sound (or light) levels. You will show the user the current level on the LEDs. 
</div>
<div>
![The microbit simulator displaying a bar graph of the current sound level. The level is dragged up and down, the bar graph grows and shrinks with the sound level.](images/sound-level-demo.gif){:width="300px"}
</div>
</div>

### Opening MakeCode

To get started creating your micro:bit project, you will need to open the MakeCode editor.

--- task ---

Open the MakeCode editor at [makecode.microbit.org](https://makecode.microbit.org){:target="_blank"}

--- collapse ---

---
title: Offline version of the editor
---

There is also a [downloadable version of the MakeCode editor](https://makecode.microbit.org/offline-app){:target="_blank"}.

--- /collapse ---

--- /task ---

Once the editor is open, you will need to create a New Project and give your project a name. 

--- task ---

Click on the **New Project** button.

![The new project button inside of MakeCode.](images/new-project-button.png)

--- /task ---

--- task ---

Give your new project the name `sound level meter` and click **Create**.

![The name 'sound level meter ' written in the New Project dialogue box.](images/soundlevel-meter.png)

**Tip:** Give your project a helpful name that relates to the activity you’re creating. This will make it easier to find if you create other projects on MakeCode.

--- /task ---

[[[makecode-tour]]]

### Plot a graph of the sound level

In this project, you will make use of the 'on start' block but not the 'forever' block. 

You can delete the 'forever' block now by dragging it to the menu panel.

![Animation showing the forever block being deleted](images/delete-forever.gif)

--- task ---

From the <code style="background-color: #00AA00">Loops</code> menu, drag out an 'every 500 ms' block and place it on the code editor panel

![The Loops menu, open with the 'every 500 ms' block highlighted](images/every-500ms.png)

--- /task ---

The microbit already has a built in sound level feature so you can use this.

--- task ---

From the <code style="background-color: #5C2D91">Led</code> menu drag a 'plot bar graph of' block.

![The Led menu, open with the 'plot bar graph of' block highlighted](images/plot-bargraph.png)

Place it inside the ''every 500 ms' block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_LheU15Tfr59C" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

From the <code style="background-color: #D400D4">Input</code> menu, drag out a 'sound level' block and place it inside the first '0' on the 'plot bar graph of' block.

![Animation showing the sound level block being placed inside the first '0' on the 'plot bar graph of' block ](images/sound-level.gif)

--- /task ---

--- task ---

Change the second '0' to '255 on the 'plot bar graph of' block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_Xbc6McLCi5gJ" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

You will now need a way of tracking the data from the sound levels. 

--- collapse ---

---
title: Installing the Data Logger extension
---

The V2 of the micro:bit has a built in data logger which enables you to track data from various sensors and inputs. You will need to install an extension to use this.

On the menu panel, click on Extensions. Another window will open showing recommended extensions. Click on the data logger and it will be installed as a menu item.

--- /collapse ---

--- task ---

From the <code style="background-color: #378273">Data Logger</code> menu, drag out a 'log data column.. value' block.

![The Data Logger menu, open with the 'log data column.. value' block highlighted](images/datalogger.png)

Place it below the 'plot bar graph of' block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_93KR1vXYFPj1" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

Inside the empty string column field on the 'log data column.. value' block, type 'Sound level'

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_JHr0atCoo2ju" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

--- task ---

From the <code style="background-color: #D400D4">Input</code> menu, drag another 'sound level' block and place it inside the '0' on the 'log data column.. value' block.

<div style="position:relative;height:calc(300px + 5em);width:100%;overflow:hidden;"><iframe style="position:relative;top:0;left:0;width:50%;height:50%;" src="https://makecode.microbit.org/---codeembed#pub:_VCJdqy3yALDh" allowfullscreen="allowfullscreen" frameborder="0" sandbox="allow-scripts allow-same-origin"></iframe></div>

--- /task ---

When you make a change to a code block in the code editor panel, the simulator will restart.

**Test** When the program runs, drag the red sound level bar up and down to change the sound levels.

**Click** The 'Show data.. Simulator' link below the micro:bit simulator to see the sound levels being logged.

![Animation showing the mic bar on the microbit simulator being dragged up and down to increase and reduce the sound. The 'Show data' button is clicked to show the data from the monitor being logged.](images/mic-test.gif)

Awesome work, you have created your first data logging program on a micro:bit!