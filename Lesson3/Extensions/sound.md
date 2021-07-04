# Applause-o-Meter
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:37405-47078-94621-47856 -->

```template
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

## Step 1

We are going to build off your Graph Louder Sounds program and add the 5 lights on the gator:bit to make an applause-o-meter that shows these lights as the sound gets louder.

## Step 2

First, change the value of ‘50’ to be your alarm value or maybe a value slightly above it. We only want to trigger the applause-o-meter for applause, not for quiet noises.

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/1cG0KVRXibqE1kTGMskL4cwI-tukBHXyh/view?usp=sharing)

#### ~ tutorialhint
Feel free to make a quick program like the one you made in Lesson 2 to get some sound readings when clapping or when not clapping.

## Step 3

Instead of the graph on the micro:bit, we are going to use the lights on the gator:bit called the neopixels. To use these, we need to first initialize them.

In ``||basic:on start||`` (Basic), use the ``||neopixel:set strip||`` (Neopixel) command and tell the micro:bit to control the NeoPixel at pin 12 (the 5 lights on the gator:bit) and that it has 5 LEDs. Leave it at GRB format.

## Step 4

Now we need to turn the neopixel’s brightness down so they do not use too much power and interfere with other sensors.

Use the ``||neopixel:set brightness||`` (Neopixel) command and set the brightness to 50.

#### ~ tutorialhint

```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
strip.setBrightness(50)
```



## step 5

Now you are going to replace the ``||led:plot bar graph||`` (Led) command with ``||neopixel:show bar graph||`` (Neopixel) command. Set the name of the variable to match the name of your neopixels (strip is the default) and make it a graph of ``||gatorMicrophone:sound intensity||`` (GatorMicrophone) that goes up to 1000. Also include a ``||basic:clear screen||`` (Basic) command to remove the smiley face.

## step 6

Congratulations, you're done!

#### ~ tutorialhint

Here is one example of what it could look like although you may have an ‘alarm value’ other than 200:
```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
basic.forever(function () {
    if (gatorMicrophone.getSoundIntensity() > 200) {
        basic.clearScreen()
        strip.showBarGraph(gatorMicrophone.getSoundIntensity(), 1000)
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

```ghost
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
basic.forever(function () {
    if (gatorMicrophone.getSoundIntensity() > 200) {
        basic.clearScreen()
        strip.showBarGraph(gatorMicrophone.getSoundIntensity(), 1000)
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
neopixel=github:microsoft/pxt-neopixel#v0.7.3
```    
