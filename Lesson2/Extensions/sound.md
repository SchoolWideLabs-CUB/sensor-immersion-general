# graph sound tutorial
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gatorMicrophone to display sound values as a graph on your micro:bit
 
Submit your final code to your teacher on schoology (or wherever your teacher asks)
  
## Step 2
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
To start, use the ``||led:plot bar graph||`` command to display a number as a graph on your micro:bit led screen
 
#### ~ tutorialhint
Try clicking on the 'Led' drawer to find the block you need!
 
```blocks
basic.forever(function () {
    led.plotBarGraph(
    0,
    0
    )
})
 
```
 
## Step 3
 
Now change the value being graphed to be the sound with ``||gator:sound intensity||`` 
 
 
#### ~ tutorialhint
 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorMicrophone.getSoundIntensity())
})
```   
 
## step 4 
 
Finally, you need to specify the value that is the top of the graph (y-axis). Most sounds do not go over 2000, so let’s make that value 2000
 
 
### ~ tutorialhint
```blocks
basic.forever(function () {
    led.plotBarGraph(
    gatorMicrophone.getSoundIntensity(),
    2000
    )
})
```
 
## step 5
Great! You did it. Now you can test it out. Does the graph change as the sound changes? What happens if you change the ``||led:up to||`` value for the ``||led.plotBarGraph||`` ?
 
 
```ghost
 
basic.forever(function () {
    led.plotBarGraph(
    gatorMicrophone.getSoundIntensity(),
    2000
    )
})
if (0 * 0 == 0 + 0) {
    
}
 
```
 
```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
```
