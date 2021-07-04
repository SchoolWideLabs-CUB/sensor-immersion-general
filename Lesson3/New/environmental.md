# CO2 Alarm Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:18956-88465-30806-46716 -->

## Step 1

We are going to learn how to use a micro:bit and gator:bit environmental sensor to create a CO2 Alarm.

```template
gatorEnvironment.beginEnvironment()
basic.forever(function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.eCO2)))
})
```

## Step 2

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/1bxYGD53_5G7AXUVdqf0oQRN7OQ0Bnc9e/view?usp=sharing)

## Step 3

First we need to 'calibrate' the sensor to find what values for CO2 are above normal and should sound the alarm. Use your skills from Lesson 2 to determine the current level of CO2 in the room.


#### ~ tutorialhint

Your code from Lesson 2 has already been placed here, run it on the micro:bit to find your room's CO2 level!

## Step 4

Now that you know what the CO2 level is in the room, pick a number that is higher than it. We are going to program the alarm to sound if the CO2 goes above this value.  

## Step 5

We need to set a logic command to test if the measured CO2 is below your selected 'alarm value'. Use the ``||logic.0 < 0||`` (Logic) to write this logic command. You need to use ``||gatorEnvironment.get eCO2 value||`` (GatorEnvironment) and your 'alarm value' to fill in the logic command.

You want the logic command to see if the sensor's CO2 value is less than (<) your 'alarm value'.

#### ~ tutorialhint
Remember that order matters, the get CO2 needs to be on the pointy side and the 'alarm value' needs to be on the side where the < opens towards.


![Alarm Value Logic](https://schoolwidelabs.github.io/sensor-immersion/images/co2.png)


## Step 6

Now that we have the 'alarm value' logic, it is time to make an ``||logic:if else statement||`` (Logic) to tell the micro:bit what to do when the values are BELOW this value... that is, when the alarm is not going off.

Inside your ``||basic:forever loop||`` (Basic), use your ``||logic:if else statement||`` (Logic), the ``||basic:show icon||`` (Basic) block, and the ``||basic:pause||`` (Basic) commands to determine what happens when the CO2 observed is below the alarm value. Adding a pause after you show the icon keeps it from going too fast.

Remember, this is if the CO2 levels are BELOW your alarm value, so make it a happy icon!

#### ~ tutorialhint
It will look like this, although you may have an 'alarm value' other than 1000
```blocks
basic.forever(function () {
    if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 1000) {
        basic.showIcon(IconNames.Happy)
        basic.pause(1000)
    } else {

    }
})
```

## Step 7

The final step is to tell the micro:bit what to do if the observed CO2 value is NOT below your 'alarm value'. This goes in the ``||logic:else||`` (Logic) part of the ``||logic:if else statement||`` (Logic).

We recommend you have a ``||basic:show icon||`` (Basic), ``||music:play tone||`` (Music), and ``||basic:pause||`` (Basic) commands in that order. The Icon and Music Tone should be alarming, as this is an alarm!

## Step 8

Congratulations, you're done!

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
