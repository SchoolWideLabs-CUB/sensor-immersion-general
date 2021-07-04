# Graph Louder Sounds
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:82298-27799-32288-66422 -->

## Step 1

We are going to learn how to use a micro:bit and GatorMicrophone to graph the sound values if they are loud enough to hear.

```template
basic.forever(function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity())
})
```

## Step 2

Describe your plan for getting the micro:bit to display the sound intensity.

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/1cG0KVRXibqE1kTGMskL4cwI-tukBHXyh/view?usp=sharing)

## Step 3

First we need to 'calibrate' the sensor to find the 'alarm value' for sound that is considered loud enough. Values above this will trigger the micro:bit to start graphing the sound intensity. Values below this will trigger the micro:bit to show an icon instead of a graph. Use your skills from Lesson 2 to determine what the sensor reads for loud and quiet noises.

#### ~ tutorialhint

We have provided your code from Lesson 2 to start with. Run it with the micro:bit to help find your 'alarm value'!

## Step 4

We need to set a logic command to test if the measured sound intensity is above your selected 'alarm value'. Use the ``||logic.0 < 0||`` (Logic) to write this logic command. You need to use the ``||gatorMicrophone:sound intensity||`` (GatorMicrophone) command and your 'alarm value' to fill in the logic command.

You want the logic command to see if the sensor's sound value is greater than (>) your 'alarm value'. It may be easier to think about if you use the dropdown in the ``||logic.0 < 0||`` (Logic) statement to change it to a ``||logic.0 > 0||`` (Logic) statement.

#### ~ tutorialhint
Remember that order matters, the 'alarm value' needs to be on the pointy side and the ``||gatorMicrophone:sound intensity||`` (GatorMicrophone) needs to be on the side where the < or > opens towards.

![Alarm Value Logic](https://schoolwidelabs.github.io/sensor-immersion/images/sound.png)

## step 5

You are going to be graphing the sound on the micro:bit with the ``||led:plot bar graph||`` (Led) command. The first number is the value to be graphed, use ``||gatorMicrophone:sound intensity||`` (GatorMicrophone). The 'up to' number is the top of the graph. Enter the highest (loudest) value you have seen for the sound sensor or maybe something a little above this. Feel free to play with this number and see what you like best.

#### ~ tutorialhint
```blocks
basic.forever(function () {
    led.plotBarGraph(
    gatorMicrophone.getSoundIntensity(),
    2000
    )
})
```

## Step 6

Now that we have the 'alarm value' logic, it is time to make an ``||logic:if else statement||`` (Logic) to tell the micro:bit what to do when the values are ABOVE this value.

In your ``||basic:forever||`` (Basic) block, use the ``||logic:if else statement||`` (Logic), your logic command, and the ``||led:plot bar graph||`` (Led) command to determine what happens when the ``||gatorMicrophone:sound intensity||`` (GatorMicrophone) observed is above the alarm value.

#### ~ tutorialhint
It will look like this, although you may have an 'alarm value' other than 2000.

```blocks
basic.forever(function () {
    if (gatorMicrophone.getSoundIntensity() > 50) {
        led.plotBarGraph(
        gatorMicrophone.getSoundIntensity(),
        2000
        )
    } else {

    }
})
```

## Step 7

The final step is to tell the micro:bit what to do if the observed sound value is NOT above your 'alarm value'. This goes in the 'else' part of the ``||logic:if else statement||`` (Logic).

We recommend you use a ``||basic:show icon||`` (Basic) command. Choose whatever icon you want!

## Step 8

Congratulations, you're done!

#### ~ tutorialhint

Here is one example of what it could look like:
```blocks
basic.forever(function () {
    if (gatorMicrophone.getSoundIntensity() > 50) {
        led.plotBarGraph(
        gatorMicrophone.getSoundIntensity(),
        2000
        )
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity()))
})
basic.forever(function () {
    if (gatorMicrophone.getSoundIntensity() > 50) {
        led.plotBarGraph(
        gatorMicrophone.getSoundIntensity(),
        2000
        )
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
```
