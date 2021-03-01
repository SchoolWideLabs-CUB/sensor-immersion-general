# show sound tutorial
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gatorMicrophone to display sound values
 
```template
input.onButtonPressed(Button.A, function () {
    
})
```
 
## Step 2
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
## Step 3
 
To start, use the ``||basic:show number||`` command to display any number when button a is pressed
 
#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!
 
```blocks
input.onButtonPressed(Button.A, function () {
	basic.showNumber(0)
})
```
 
## Step 4
 
Now change the value of ``||basic:showNumber||`` to be the sound with ``||gatorMicrophone:sound.intensity||`` 
 
 
#### ~ tutorialhint
 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorMicrophone.getSoundIntensity())
})
```
 
## step 5 
 
In the ``||math.math||`` menu you will find the ``||math.round||`` command to round to the nearest whole number
 
Use this command to change the displayed value to be the sound rounded to the nearest whole number
 
### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity())
})
```
 
## step 6
Great! You did it. Now you can test it out. How could you use the Math buttons to change the display to show a one or two digit number for normal sound inputs?
 
 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity()))
})
if (0 * 0 == 0 + 0) {
    
}
 
```
 
```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
```