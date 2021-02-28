# graph louder sounds
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gatorMicrophone to graph the sound values if they are loud enough to hear
 
Submit your answers using the google form linked on [this page](https://schoolwidelabs.github.io/sensor-immersion/assessments/Lesson3/sound_assessment.html) under your teacher's name. 
 
## Step 2
 
**Before you begin, answer question 1 on the google form**
 
Describe your plan for getting the microbit to display the sound intensity
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
## Step 3
 
First we need to 'calibrate' the sensor to find the 'alarm value' for sound that is considered loud enough. Values above this will trigger the microbit to start graphing the sound intensity. Values below this will trigger the microbit to show an icon instead of a graph. Use your skills from Lesson 2 to determine what the sensor reads for loud and quiet noises. 
 
**Enter these values on questions 2 and 3 on the google form**
 
## Step 4
 
We need to set a logic command to test if the measured sound is above your selected 'alarm value'. Use the 'Sound Intensity'  and ' 0 < 0 ' commands to write this logic statement for when the observed soil moisture is greater than (>) your 'alarm value'. 
 
Note that you may need to flip the < to a > depending on where you put the 'get moisture' command
 
#### ~ tutorialhint
Remember that order matters, the 'alarm value' needs to be on the pointy side and the get sound needs to be on the side where the < opens towards. 
 

![Alarm Value Logic](https://schoolwidelabs.github.io/sensor-immersion/images/sound.png)
 
## step 5
 
You are going to be graphing the sound on the microbit with the 'Plot Bar Graph' command. The first number is the value to be graphed, use 'Sound Intensity'. The 'up to' number is the top of the graph. Enter the highest (loudest) value you have seen for the sound sensor or maybe something a little above this. Feel free to play with this number and see what you like best.
 
## Step 6
 
Now that we have the 'alarm value' logic, it is time to make an if statement to tell the microbit what to do when the values are ABOVE this value.
 
Use the forever, 'Plot Bar Graph' and 'If Else' and commands to determine what happens when the sound intensity observed is above the alarm value.
 
#### ~ tutorialhint
It will look like this, although you may have an 'alarm value' other than 1500
```blocks
basic.forever(function () {
    if (gatorMicrophone.getSoundIntensity() > 50) {
        led.plotBarGraph(
        gatorMicrophone.getSoundIntensity(),
        1500
        )
    } else {
    	
    }
})
```
 
## Step 7
 
The final step is to tell the microbit what to do if the observed sound value is NOT above your 'alarm value'. This goes in the 'else' part of the 'If Else' command. 
 
We recommend you have a 'Show Icon' command.
 
## Step 8
 
Congratulations, you're done!
 
**Fill out the final questions in the google form**
 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity()))
})
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
 
```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
```
