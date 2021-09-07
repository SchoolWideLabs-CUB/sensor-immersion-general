# Soil Moisture Alarm Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:70891-89974-16308-37681 -->

## Step 1

We are going to learn how to use a micro:bit and gator:soil moisture sensor to sound an alarm if the soil gets too dry.

```template
basic.forever(function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```

## Step 2

First, make sure your gator:soil sensor is correctly wired to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/18e1Yyj8VSsILIePJkI6tx6cDbjrS48s8/view?usp=sharing)

## Step 3

First, we need to figure out how dry is too dry. To do this, we need to run tests on dry soil and wet soil to figure out at what value we want our alarm to go off. Values from the sensor below this will sound the alarm.

Use your skills from Lesson 2 to determine what the sensor reads for wet and dry soil. If you do not have plants or soil to test with, use a cup of water for wet soil and the air for dry soil.

#### ~ tutorialhint

We have provided your code from Lesson 2 to start with. Run it with the micro:bit to help find your 'alarm value'!

## Step 4

Now that you know what the soil moisture is for dry and wet soil, pick a number that is between the two. We are going to program the alarm to sound if the soil moisture falls below this value.

We will call this number your 'alarm value' for the rest of the tutorial.

## Step 5

Now that we have the 'alarm value', it is time to make an ``||logic:if else statement||`` (Logic) to tell the micro:bit what to do when the soil moisture is ABOVE this value... that is, when the alarm is not going off.

Inside your ``||basic:forever||`` (Basic) event, create an ``||logic:if else statement||`` (Logic). There are two spots to place blocks here: in the ``||logic:if||`` and the ``||logic:else||``. For our program, we want the code in the ``||logic:if||`` side to run when the alarm is not going off.

In the ``||logic:if||`` section, create code to show that the alarm is not going off using a ``||basic:show icon||`` (Basic) block. Remember, this is a good thing, so make it a happy icon!


#### ~ tutorialhint
It will look something like this:
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
Now, we need to create a Logic hexagon block (or hex block) to test if the measured soil moisture value from the sensor is above your selected 'alarm value'. Use the ``||logic.0 < 0||`` (Logic) hex block to write this in code. You need to use ``||gatorSoil.get moisture||`` (GatorSoil) and your 'alarm value' to fill in the Logic hex block.

You want the logic command to check if the sensor's moisture value is greater than (>) your 'alarm value'.

#### ~ tutorialhint
Remember that order matters, the ``||gatorSoil:get moisture||`` oval (GatorSoil) needs to be on the open side and your 'alarm value' needs to be on the pointy side.

![Alarm Value Logic](https://schoolwidelabs.github.io/sensor-immersion/images/soil_code.png)

## Step 7

The final step is to tell the micro:bit what to do if the measured soil moisture value is below your 'alarm value'. This goes in the ``||logic:else||`` part of the ``||logic:if else statement||`` (Logic). This is because if the measured value is above the value, it would run the blocks in the ``||logic:if||`` section instead!

We recommend you have a ``||basic:show icon||`` (Basic), ``||music:play tone||`` (Music), and ``||basic:pause||`` (Basic) blocks in that order. The Icon and Music Tone should be alarming, make it whatever you want!

#### ~ tutorialhint

Here is one example of what it could look like:

```blocks
basic.forever(function () {
    if (gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1) > 0.5) {
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

If you want to make more complicated rhythms with ``||music:Music||``, head to the next tutorial!

```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2)))
})
basic.forever(function () {
    if (gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2) > 0.5) {
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
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
