# Graph Quieter Sounds micro:bit v2 no gator:bit
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:14790-80668-92112-18445 -->

## Step 1

We are going to program the micro:bit to show a graph of the sound values measured by the micro:bit v2 microphone (sound sensor).

When the sound gets too loud, we are going to show an icon instead of the sound values. Let's get started!

```template
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(input.soundLevel()))
})
```

## Step 2

First, we need to run the code below to see what sound values are normal for our classroom! Download the code and see what values are being displayed on your micro:bit! 

Now, pick a value that is a little higher than the loudest value you recorded! We will call this our 'too loud' value.

Once you have your 'too loud' value, move on to Step 3!

#### ~ tutorialhint

You don't need to change the code yet! Simply download it and record the numbers you see to find your 'too loud' value.

## Step 3

Now that we have our 'too loud' value, it is time to make an ``||logic:if else statement||`` (Logic) to tell the micro:bit what to do when the sound values are ABOVE this value!

Inside your ``||basic:forever||`` (Basic) event, create an ``||logic:if else statement||`` (Logic). There are two spots to place blocks here: in the ``||logic:if||`` and the ``||logic:else||``. For our program, we want the code in the ``||logic:if||`` side to run when the measured sound values are too loud.

In the ``||logic:if||`` event, create code to show that it is too loud using a ``||basic:show icon||`` (Basic) block and a ``||music:play tone||`` (Music) block. Remember, this is a something that we don't want to happen, so make it a bad thing!

#### ~ tutorialhint

Feel free to remove your ``||basic:show number||`` block, you won't need it anymore. Remember, this is telling us it is too loud in the classroom, so we want it to be noticeable and bad!

```blocks
basic.forever(function () {
    if (true) {
        basic.showIcon(IconNames.Sad)
        music.playTone(554, music.beat(BeatFraction.Whole))
    } else {

    }
})
```

## step 4
Now, we need to create a Logic hexagon block (or hex block) to check if the measured sound intensity from the sensor is greater than your selected 'too loud' value. Use the ``||logic.0 < 0||`` (Logic) hex block to write this in code and place it in the hex block labeled true.

You need to use ``||input:sound value||`` (Input) and your 'too loud' value to fill in the Logic hex block.

You want the logic command to check if the value from the microphone on the v2 microbit, measured by ``||input:sound value||``, is greater than (>) your 'alarm value'.

#### ~ tutorialhint
Remember that order matters, the ``||input:sound value||`` oval (Input) needs to be on the open side and your 'too loud' value needs to be on the pointy side (your 'too loud' value should be bigger than 50).

![Alarm Value Logic](https://schoolwidelabs.github.io/sensor-immersion/images/sound.png)

## Step 5

Next, we need to use the ``||logic:else||`` event to graph our ``||input:sound value||`` (Input). To do this, we need to use the ``||led:plot bar graph||`` (Led) block! This takes in two values, a value to be graphed (the first oval) and the maximum value of the graph (the second oval).

In the first oval, the value to be graphed, we need to put our ``||input:sound value||`` from the microphone (sound sensor) on the v2 micro:bit. This way the graph will show the measured sound intensity in the classroom, which will change often!

In the second oval, we need the maximum value that can be graphed. Think of this as the top of the y-axis from math class! In this program, the maximum value to be graphed is your 'too loud' value.

#### ~ tutorialhint

Keep in mind, in this example the 'too loud' value is 1500. Yours may be different!

```blocks
basic.forever(function () {
    if (input.soundLevel() > 1500) {
        basic.showIcon(IconNames.Sad)
        music.playTone(554, music.beat(BeatFraction.Whole))
    } else {
    led.plotBarGraph(
        input.soundLevel(),
        1500
        )
    }
})
```

## Step 6

Congratulations, you're done!


```ghost
basic.forever(function () {
    if (input.soundLevel() > 1500) {
        basic.showIcon(IconNames.Sad)
        music.playTone(554, music.beat(BeatFraction.Whole))
    } else {
    led.plotBarGraph(
        input.soundLevel(),
        1500
        )
    }
})
```
