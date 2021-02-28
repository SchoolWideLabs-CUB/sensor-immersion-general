# soil moisture with lights
### @explicitHints true
 
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
 
We are going to build off your Graph Soil Moisture program and tell the neopixels on the gator:bit to make plot a bar that ticks down as the plant dries out. If the plant is wet, the micro:bit will show a smiley face. 
 
Submit your final code to your teacher on schoology (or wherever your teacher asks)
 
## Step 2
 
First, change the value of ‘0.5’ to be your old alarm value or maybe a value slightly above it. We only want to trigger the dry soil graph after the plant has started to dry out, not when it is fully watered. This value is called your ‘new alarm value’.
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
#### ~ tutorialhint
Feel free to make a quick program like the one you made in lesson 2 to get some sound readings of different soils. If you do not have access to dirt and water, you can use a cup of water to get the wet reading and the air to get the dry reading.
 
## Step 3
 
Insead of the showing icons, pausing and playing music with the micro:bit we are going to use the lights on the gator:bit called the neopixels. To use these, we need to first initialize them.
 
``||basic: On start||`` use the ``||neopixel:set strip||`` command and tell the micro:bit to control the NeoPixel at pin 12 (on the gator:bit) and that it has 5 LEDs. Leave it at GRB format. 
 
## Step 4
 
Now we need to turn the neo pixel’s brightness down so they do not use too much power and interfere with other sensors.
 
Use the ``||neopixel:set brightness||`` command and set the brightness to 50.
 
#### ~ tutorialhint
```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
strip.setBrightness(50)
```
 
## step 5
 
Now you are going to replace the ``||basic:show icon||`` frown, ``||basic:pause||`` and ``||music:play tone||`` commands under ‘else’ with ``||neopixel:show bar graph||`` command. Set the name of the variable to match the name of your neopixels (strip is the default) and make it a graph of ``||gator:get moisture||`` that goes up to the new alarm value. Also include a ``||basic:clear screen||`` command so the smiley face in the top condition turns off. 
 
#### ~ tutorialhint
Removing the pause commands is optional, see how it changes the behavior of your program.
 
## step 6
 
Congratulations, you're done!
 
#### ~ tutorialhint
 
Here is one example of what it could look like although you may have an ‘alarm value’ other than 0.5:
```blocks
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

 
