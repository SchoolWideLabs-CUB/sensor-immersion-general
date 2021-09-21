# Soil Moisture With Lights
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:28058-16714-85501-26992 -->

```template
basic.showIcon(IconNames.Yes)
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

First, make sure your gator:soil sensor is still wired correctly to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/12oWXe1Icgzu3zD3qE00i4QrkLfok5Tlvc9vSgI2yB3g/edit?usp=sharing)

## Step 3

First, change the value of ‘0.5’ to be your old alarm value or a value slightly above it. We only want to trigger the dry soil graph after the plant has started to dry out, not when it is fully watered. This value is called your ‘new alarm value’.

Instead of using ``||basic:show icon||``, ``||music:play tone||``, and ``||basic:pause||`` on the micro:bit we are going to use the lights on the gator:bit, which are called the ``||Neopixel:Neopixels||``. To use them, we need to first initialize them.

In the ``||basic:on start||`` (Basic) event, use the ``||neopixel:set strip||`` (Neopixel) block and tell the micro:bit to control the NeoPixel at pin 12 (these are the ones on the gator:bit) and that it has 5 LEDs. Leave it at GRB format.

## Step 4

Now we need to turn the Neopixel’s brightness down so they do not use too much power and interfere with other sensors.

In the ``||basic:on start||`` event, use the ``||neopixel:set brightness||`` (Neopixel:more) block to set the brightness to 50.

#### ~ tutorialhint
```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
strip.setBrightness(50)
```

## step 5

Now you are going to replace the ``||basic:show icon||`` frown, ``||music:play tone||``, and ``||basic:pause||`` blocks in the ``||Logic:else||`` event with the ``||neopixel:show bar graph||`` (Neopixel) block.

Set the name of the variable to match the name of your Neopixels (``||Variables:strip||`` is the default) and make it a graph of GatorSoil's ``||gator:get moisture||`` ``||Neopixel:up to||`` the 'new alarm' value.

Also include a ``||basic:clear screen||`` (Basic) block inside the ``||Logic:else||`` event so the smiley face in the top condition turns off. Feel free to replace the icon with something else!

#### ~ tutorialhint
Removing the ``||basic:pause||`` (Basic) commands is optional, see how it changes the behavior of your program.

## step 6

Congratulations, you're done!

#### ~ tutorialhint

Here is one example of what it could look like although you may have an ‘alarm value’ other than 0.5:
```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
strip.setBrightness(50)
basic.showIcon(IconNames.Yes)
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
