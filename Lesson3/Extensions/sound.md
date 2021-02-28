 
# applause-o-meter
### @explicitHints true
 
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
 
We are going to build off your Graph Louder Sounds program and add neopixels on the gator:bit to make an applause-o-meter that has a bar that lights up as the sound gets louder. 
 
Submit your final code to your teacher on schoology (or wherever your teacher asks)
 
## Step 2
 
First, change the value of ‘50’ to be your alarm value or maybe a value slightly above it. We only want to trigger the applause-o-meter for applause, not more quiet noises.
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
#### ~ tutorialhint
Feel free to make a quick program like the one you made in lesson 2 to get some sound readings when clapping or when not clapping.
 
## Step 3
 
Insead of the graph on the micro:bit we are going to use the lights on the gator:bit called the neopixels. To use these, we need to first initialize them.
 
Use the ``||neopixel:set strip||`` command and tell the micro:bit to control the NeoPixel at pin 12 (on the gator:bit) and that it has 5 LEDs. Leave it at GRB format. 
 
## Step 4
 
Now we need to turn the neo pixel’s brightness down so they do not use too much power and interfere with other sensors.
 
Use the ``||neopixel:set brightness||`` command and set the brightness to 50.
 
#### ~ tutorialhint
```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
strip.setBrightness(50)
```
 
Replace with strip show bar graph up to 1500
 
## step 5
 
Now you are going to replace the ``||led:plot bar graph||`` command with ``||neopixel:show bar graph||`` command. Set the name of the variable to match the name of your neopixels (strip is the default) and make it a graph of ``||gator:Sound Intensity||`` that goes up to 1000. Also include a ``||basic:clear screen||`` command to remove the smiley face. 
 
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
