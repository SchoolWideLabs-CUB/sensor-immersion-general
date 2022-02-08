# Applause-o-Meter
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:92199-60888-44740-20925 -->

```template
basic.showIcon(IconNames.Yes)
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

## Step 1

We are going to build off your Graph Louder Sounds program and add the 5 lights on the gator:bit to make an applause-o-meter that shows these lights as the sound gets louder!

## Step 2
First, make sure that your gator:microphone is still wired correctly to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/1oiQ0SdTL-UBnaFOiDmDOU_auGtIwzq84lymv9pf5Y0E/edit?usp=sharing)

## Step 3
First, change the value of '50' to be much higher. We only want to trigger the applause-o-meter for applause, not for quiet noises.

You might need to experiment with this value to find the right noise level for your classroom.

#### ~ tutorialhint
This new value should be in the area of roughly 500. We don't want talking to pick up on it, we only want to see it during applause.

## Step 4
Instead of using ``||led:plot bar graph||`` on the micro:bit, we are going to use the lights on the gator:bit called the ``||Neopixel:Neopixels||``. To use these, we need to first initialize them.

In the ``||basic:on start||`` (Basic) event, use the ``||neopixel:set strip||`` (Neopixel) block and tell the micro:bit to control the NeoPixels at pin 12 (the 5 lights on the gator:bit) and that it has 5 LEDs. Leave it at GRB format.

## Step 5

Now we need to turn the Neopixel’s brightness down so they do not use too much power and interfere with other sensors.

Use the ``||neopixel:set brightness||`` (Neopixel:more) block to set the brightness to 50.

#### ~ tutorialhint

```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
strip.setBrightness(50)
```

## step 6

Now you are going to replace the ``||led:plot bar graph||`` (Led) block with the ``||neopixel:show bar graph||`` (Neopixel) block. Make it a graph of ``||gatorMicrophone:sound intensity||`` (GatorMicrophone) that goes ``||Neopixel:up to||`` 2000.

Also include a ``||basic:clear screen||`` (Basic) block above the ``||neopixel:show bar graph||`` block to remove the smiley face.

#### ~ tutorialhint

Here is one example of what it could look like although you may have a value other than 500 in your ``||Logic:0 > 0||`` hex block.
```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
basic.showIcon(IconNames.Yes)
basic.forever(function () {
    if (gatorMicrophone.getSoundIntensity() > 500) {
        basic.clearScreen()
        strip.showBarGraph(gatorMicrophone.getSoundIntensity(), 2000)
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

## step 7

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
