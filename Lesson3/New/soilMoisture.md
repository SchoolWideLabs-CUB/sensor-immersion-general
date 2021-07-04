# Soil Moisture Alarm Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:97046-52804-13459-19788 -->

## Step 1

We are going to learn how to use a micro:bit and gator:bit soil moisture sensor  to sound an alarm if the soil gets too dry.

```template
basic.forever(function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```

## Step 2

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/18e1Yyj8VSsILIePJkI6tx6cDbjrS48s8/view?usp=sharing)

## Step 3

First we need to ‘calibrate’ the sensor to find the ‘alarm value’ for soil moisture that is considered too dry. Values below this will sound the alarm. Use your skills from Lesson 2 to determine what the sensor reads for wet and dry soil. If you do not have plants or soil to test with, use a cup of water for wet soil and the air for dry soil.

#### ~ tutorialhint

We have provided your code from Lesson 2 to start with. Run it with the micro:bit to help find your 'alarm value'!

## Step 4

We need to set a logic command to test if the measured soil moisture is above your selected 'alarm value'. Use the ``||logic.0 < 0||`` (Logic) to write this logic command. You need to use the ``||gatorSoil.get moisture||`` (GatorSoil) command and your 'alarm value' to fill in the logic command.

You want the logic command to see if the sensor's moisture value is greater than (>) your 'alarm value'. It may be easier to think about if you use the dropdown in the ``||logic.0 < 0||`` (Logic) statement to change it to a ``||logic.0 > 0||`` (Logic) statement.

#### ~ tutorialhint
Remember that order matters, the 'alarm value' needs to be on the pointy side and the ``||gatorSoil:get moisture||`` (GatorSoil) needs to be on the side where the < or > opens towards.

![Alarm Value Logic](https://schoolwidelabs.github.io/sensor-immersion/images/soil_code.png)

## Step 5

Now that we have the 'alarm value' logic, it is time to make an ``||logic:if else statement||`` (Logic) to tell the micro:bit what to do when the soil moisture is ABOVE this value... that is, when the alarm is not going off.

Inside your ``||basic:forever loop||`` (Basic), use your ``||logic:if else statement||`` (Logic), the ``||basic:show icon||`` (Basic) and the ``||basic:pause||`` (Basic) commands to determine what happens when the soil moisture observed is below the alarm value. Adding a pause after you show the icon keeps it from going too fast.

Remember, this is if the soil moisture is ABOVE your alarm value, so make it a happy icon!

#### ~ tutorialhint
It will look like this, although you may have an ‘alarm value’ other than 0.5
```blocks
basic.forever(function () {
    if (gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2) > 0.5) {
        basic.showIcon(IconNames.Happy)
        basic.pause(1000)
    } else {

    }
})
```

## Step 6

The final step is to tell the micro:bit what to do if the observed soil moisture value is NOT above your 'alarm value'. This goes in the ``||logic:else||`` (Logic) part of the ``||logic:if else statement||`` (Logic).

We recommend you have ``||basic:show icon||`` (Basic), ``||music:play tone||`` (Music), and ``||basic:pause||`` (Basic) commands in that order. The Icon and Music Tone should be alarming, as this is an alarm!

## Step 7

Congratulations, you're done!

#### ~ tutorialhint

Here is one example of what it could look like:

```blocks
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
