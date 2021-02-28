# display sound tutorial
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gatorMicrophone to display sound values
 
Submit your answers using the google form linked on[this page](https://schoolwidelabs.github.io/sensor-immersion/assessments/Lesson2/sound_assessment.html) under your teacher's name. 
 
## Step 2
 
**Before you begin, answer question 1 on the google form**
 
Describe your plan for getting the microbit to display the sound intensity
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
## Step 3
 
To start, use the show number command to display any number when button a is pressed
 
#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!
 
```blocks
input.onButtonPressed(Button.A, function () {basic.showNumber(0)}
```
 
## Step 4
 
Now change the value of the shown number to be the sound intensity
 
 
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
Great! You did it. Now you can test it out. How could you use the math blocks to decrease the  sound output so the number displayed is not so large?
 
**Don't forget to fill out the final questions on the google form.**
 
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
