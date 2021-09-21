# CO2 Alarm Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:98612-62867-45871-17972 -->

## Step 1

We are going to learn how to use a micro:bit and gator:bit environmental sensor to create a CO2 Alarm!

```template
gatorEnvironment.beginEnvironment()
basic.forever(function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.eCO2)))
})
```

## Step 2

First, let's make sure that your gator:environment is wired to your gator:bit correctly.

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/1Wy_TLucsBvOR2eAHqqLUJwxPPhVsipK1Qq8MdPxL1X4/edit?usp=sharing)

## Step 3

First we need to 'calibrate' the sensor to find what values for CO2 are above normal and should sound the alarm.

Use the code below to determine the current level of CO2 in the room by downloading it to your micro:bit and writing down the value that appears.


#### ~ tutorialhint

We are going to make an alarm for when this value gets too high, so write down the highest value you see on the micro:bit! There should be some slight differences in the numbers you see. If there isn't, return to Step 2 and check the wiring of your sensor.

## Step 4

Now that you know what the CO2 level is in the room, pick a number that is a little higher than it. We are going to program the alarm to sound if the CO2 goes above this value.  

We will call this number your 'alarm value' for the rest of the tutorial.

## Step 5

Now that we have the 'alarm value', it is time to make an ``||logic:if else statement||`` (Logic) to tell the micro:bit what to do when the values are BELOW this value... that is, when the alarm is not going off.

Inside your ``||basic:forever||`` (Basic) event, create an ``||logic:if else statement||`` (Logic). There are two spots to place blocks here: in the ``||logic:if||`` and the ``||logic:else||``. For our program, we want the code in the ``||logic:if||`` side to run when the alarm is not going off.

In the ``||logic:if||`` section, create code to show that the alarm is not going off using a ``||basic:show icon||`` (Basic) block. Remember, this is a good thing, so make it a happy icon!


#### ~ tutorialhint
It will look like this, although you may have an 'alarm value' other than 1000
```blocks
basic.forever(function () {
    if (true) {
        basic.showIcon(IconNames.Happy)
    } else {

    }
})
```

If your icon disappears too fast, use a ``||basic:pause||`` (Basic) block to show it for a couple of seconds (shown below).
```blocks
basic.forever(function () {
    if (true) {
        basic.showIcon(IconNames.Happy)
        basic.pause(2000)
    } else {

    }
})
```

## Step 6
Now, we need to create a Logic hexagon block (or hex block) to test if the measured CO2 value from the sensor is below your selected 'alarm value'. Use the ``||logic.0 < 0||`` (Logic) hex block to write this in code. You need to use ``||gatorEnvironment.get eCO2 value||`` (GatorEnvironment) and your 'alarm value' to fill in the logic command.

You want the logic command to check if the sensor's CO2 value is less than (<) your 'alarm value'.

#### ~ tutorialhint
Remember that order matters, the ``||gatorEnvironment:get eCO2 value||`` oval (GatorEnvironment) needs to be on the pointy side and your 'alarm value' needs to be on the open side.

![Alarm Value Logic](https://schoolwidelabs.github.io/sensor-immersion/images/co2.png)

## Step 7

The final step is to tell the micro:bit what to do if the measured CO2 value is above your 'alarm value'. This goes in the ``||logic:else||`` part of the ``||logic:if else statement||`` (Logic). This is because if the measured value is below the value, it would run the blocks in the ``||logic:if||`` section instead!

We recommend you have a ``||basic:show icon||`` (Basic), ``||music:play tone||`` (Music), and ``||basic:pause||`` (Basic) blocks in that order. The Icon and Music Tone should be alarming, make whatever you want!

#### ~ tutorialhint

Here is one example of what it could look like:

```blocks
gatorEnvironment.beginEnvironment()
basic.forever(function () {
    if (gatorEnvironment.getMeasurement(measurementType.eCO2) <= 2000) {
        basic.showIcon(IconNames.Happy)
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Sad)
        music.playTone(554, music.beat(BeatFraction.Breve))
        basic.pause(1000)
    }
})
```

## Step 8

Congratulations, you're done!



```ghost
input.onButtonPressed(Button.A, function () {  basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.pressure)))
})
gatorEnvironment.beginEnvironment()
basic.forever(function () {
    if (gatorEnvironment.getMeasurement(measurementType.eCO2) <= 2000) {
        basic.showIcon(IconNames.Happy)
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Sad)
        music.playTone(554, music.beat(BeatFraction.Breve))
        basic.pause(1000)
    }
})
```


```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
