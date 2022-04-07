# Graph Quieter Sounds
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:55989-53790-98115-17671 -->

## Step 1

We are going to program the micro:bit to show a graph of the sound values measured by the gator:microphone.

When the sound gets too loud, we are going to show an icon instead of the sound values. Let's get started!

```template
basic.forever( function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity())
})
```

## Step 2

First, make sure the gator:microphone sensor is still wired to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/1oiQ0SdTL-UBnaFOiDmDOU_auGtIwzq84lymv9pf5Y0E/edit?usp=sharing)

## Step 3

First, we need to run the code below to see what sound values are normal for our classroom! Download the code and see what values are being displayed on your micro:bit! Make sure it's connected to the gator:bit and that the value is changing. If it isn't, go back to Step 2.

Now, pick a value that is a little higher than the loudest value you recorded! We will call this our 'too loud' value.

Once you have your 'too loud' value, move on to Step 4!

#### ~ tutorialhint

You don't need to change the code yet! Simply download it and record the numbers you see to find your 'too loud' value.

## Step 4

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

## step 5
Now, we need to create a Logic hexagon block (or hex block) to check if the measured sound intensity from the sensor is greater than your selected 'too loud' value. Use the ``||logic.0 < 0||`` (Logic) hex block to write this in code and place it in the hex block labeled true.

You need to use ``||gatorMicrophone:sound intensity||`` (GatorMicrophone) and your 'too loud' value to fill in the Logic hex block.

You want the logic command to check if the sensor's ``||gatorMicrophone:sound intensity||`` is greater than (>) your 'alarm value'.

#### ~ tutorialhint
Remember that order matters, the ``||gatorMicrophone:sound intensity||`` oval (GatorMicrophone) needs to be on the open side and your 'too loud' value needs to be on the pointy side (your 'too loud' value should be bigger than 50).

![Alarm Value Logic](https://schoolwidelabs.github.io/sensor-immersion/images/sound.png)

## Step 6

Next, we need to use the ``||logic:else||`` event to graph our ``||gatorMicrophone:sound intensity||`` (GatorMicrophone). To do this, we need to use the ``||led:plot bar graph||`` (Led) block! This takes in two values, a value to be graphed (the first oval) and the maximum value of the graph (the second oval).

In the first oval, the value to be graphed, we need to put our ``||gatorMicrophone:sound intensity||`` from the gator:microphone sensor. This way the graph will show the measured sound intensity in the classroom, which will change often!

In the second oval, we need the maximum value that can be graphed. Think of this as the top of the y-axis from math class! In this program, the maximum value to be graphed is your 'too loud' value.

#### ~ tutorialhint

Keep in mind, in this example the 'too loud' value is 1500. Yours may be different!

```blocks
basic.forever(function () {
    if (gatorMicrophone.getSoundIntensity() > 1500) {
        basic.showIcon(IconNames.Sad)
        music.playTone(554, music.beat(BeatFraction.Whole))
    } else {
    led.plotBarGraph(
        gatorMicrophone.getSoundIntensity(),
        1500
        )
    }
})
```

## Step 7

Congratulations, you're done!

If it does not work, see the hint for a few common issues!

#### ~ tutorialhint
Here are some common issues and their solutions:
1. Check for two red lights next to the 3.3V pin on the gator:bit. If they are off, check the following switch and make sure it is on.
![VOut](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/VOUT_Switch.jpg?raw=true)

2. If the speaker is not making any noise, check this switch and make sure it is on:
![Speaker](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/SPEAKER_Switch.jpg?raw=true)

3. Otherwise, double check your wiring with the wiring guide [here](https://docs.google.com/document/d/1oiQ0SdTL-UBnaFOiDmDOU_auGtIwzq84lymv9pf5Y0E/edit?usp=sharing).



```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity()))
})
basic.forever(function () {
    if (gatorMicrophone.getSoundIntensity() > 50) {
        led.plotBarGraph(
        gatorMicrophone.getSoundIntensity(),
        1500
        )
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
```
