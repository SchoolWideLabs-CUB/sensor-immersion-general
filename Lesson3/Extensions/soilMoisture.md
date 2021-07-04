# Soil Moisture With Lights
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:24742-60530-48899-27404 -->

```template
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

## Step 1

We are going to build off your Graph Soil Moisture program and tell the 5 lights on the gator:bit to plot a bar that ticks down as the plant dries out. If the plant is wet, the micro:bit will show a smiley face.

## Step 2

First, change the value of ‘0.5’ to be your old alarm value or maybe a value slightly above it. We only want to trigger the dry soil graph after the plant has started to dry out, not when it is fully watered. This value is called your ‘new alarm value’.

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/18e1Yyj8VSsILIePJkI6tx6cDbjrS48s8/view?usp=sharing)

#### ~ tutorialhint
Feel free to make a quick program like the one you made in Lesson 2 to get some moisture readings of different soils. If you do not have access to dirt and water, you can use a cup of water to get the wet reading and the air to get the dry reading.

## Step 3

Instead of using ``||basic:show icon||``, ``||music:play tone||``, and ``||basic:pause||`` on the micro:bit we are going to use the lights on the gator:bit, which are called the Neopixels. To use them, we need to first initialize them.

In ``||basic: on start||`` (Basic), use the ``||neopixel:set strip||`` (Neopixel) command and tell the micro:bit to control the NeoPixel at pin 12 (these are the ones on the gator:bit) and that it has 5 LEDs. Leave it at GRB format.

## Step 4

Now we need to turn the Neopixel’s brightness down so they do not use too much power and interfere with other sensors.

Use the ``||neopixel:set brightness||`` (Neopixel) command and set the brightness to 50.

#### ~ tutorialhint
```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
strip.setBrightness(50)
```

## step 5

Now you are going to replace the ``||basic:show icon||`` frown, ``||basic:pause||`` and ``||music:play tone||`` commands under ‘else’ with ``||neopixel:show bar graph||`` (Neopixel) command.

Set the name of the variable to match the name of your Neopixels (strip is the default) and make it a graph of ``||gator:get moisture||`` (GatorSoil) that goes up to the new alarm value.

Also include a ``||basic:clear screen||`` (Basic) command so the smiley face in the top condition turns off.

#### ~ tutorialhint
Removing the ``||basic:pause||`` (Basic) commands is optional, see how it changes the behavior of your program.

## step 6

Congratulations, you're done!

#### ~ tutorialhint

Here is one example of what it could look like although you may have an ‘alarm value’ other than 0.5:
```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
strip.setBrightness(50)
basic.forever(function () {
    if (gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1) > 0.5) {
        basic.showIcon(IconNames.Happy)
    } else {
        basic.clearScreen()
        strip.showBarGraph(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1), 0.5)
    }
})

```

```ghost
input.onButtonPressed(Button.A, function () {
    led.plotBarGraph(
    Math.round(0),
    0
    )
    basic.showNumber(Math.round(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1)))
    basic.pause(100)
})
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
strip.setBrightness(50)
basic.forever(function () {
    if (gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1) < 0.5) {
        basic.clearScreen()
        strip.showBarGraph(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1), 0.5)
    } else {
        basic.showIcon(IconNames.Happy)
    }
})

```


```package
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3

neopixel=github:microsoft/pxt-neopixel#v0.7.3

```
