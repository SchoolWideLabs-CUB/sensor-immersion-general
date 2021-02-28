# sound an alarm if CO2 drops below a certain threshold
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gator:bit environmental sensor  to sound an alarm if CO2 gets too high
 
Submit your answers using the google form linked on [this page](https://schoolwidelabs.github.io/sensor-immersion/assessments/Lesson3/environmental_assessment.html) under your teacher's name. 
 
  
## Step 2
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
To start, use the GatorEnvironment ‘initialize’ command start the sensor when the program starts`	
 
 
## Step 3
 
First we need to ‘calibrate’ the sensor to find what values for CO2 are above normal and should sound the alarm. Use your skills from Lesson 2 to determine the current level of CO2 in the room. 
 
**Enter this value on question 2 on the google form**
 
#### ~ tutorialhint
 
You are going to need to make a temporary program or use an old program (from Lesson 2) that has the ‘show value’ and gator environment ‘get’ commands. 
 
## Step 4
 
Now that you know what the CO2 level is in the room, pick a number that is higher than it. We are going to program the alarm to sound if the CO2 goes above this value.  
 
**Enter this ‘alarm value’ on question 3 on the google form**
 
## Step 5
 
We need to set a logic command to test if the measured CO2 is below your selected ‘alarm value’. Use the gator environment ‘get’ and ‘ 0 < 0 ‘  commands to write this logic statement for when the observed CO2 is less than (<) your ‘alarm value’. 
 
#### ~ tutorialhint
Remember that order matters, the get CO2 needs to be on the pointy side and the ‘alarm value’ needs to be on the side where the < opens towards. 
 

![Alarm Value Logic](https://schoolwidelabs.github.io/sensor-immersion/images/co2.png)
 
## Step 6
 
Now that we have the ‘alarm value’ logic, it is time to make an if statement to tell the microbit what to do when the values are BELOW this value... that is, when the alarm is not going off.
 
Use the forever, ‘Show Icon’, ‘Pause’ and ‘If Else’ and commands to determine what happens when the CO2 observed is below the alarm value. Adding a pause after you show the icon keeps it from going too fast. 
 
#### ~ tutorialhint
It will look like this, although you may have an ‘alarm value’ other than 1000
```blocks
basic.forever(function () {
    if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 1000) {
        basic.showIcon(IconNames.Happy)
        basic.pause(1000)
    } else {
    	
    }
})
```
 
## Step 7
 
The final step is to tell the microbit what to do if the observed CO2 value is NOT below your ‘alarm value’. This goes in the ‘else’ part of the ‘If Else’ command. 
 
We recommend you have a ‘show icon’, ‘play tone’ and ‘pause’ commands in that order. Also, the icon should be different from when the alarm is not going off. 
 
## Step 8
 
Congratulations, you're done!
 
**Fill out the final questions in the google form**
 
```ghost
input.onButtonPressed(Button.A, function () {  basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.pressure)))
})
gatorEnvironment.beginEnvironment()
basic.forever(function () {
    if (gatorEnvironment.getMeasurement(measurementType.eCO2) <= 2000) {
        basic.showIcon(IconNames.Happy)
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Sad)
        music.playTone(554, music.beat(BeatFraction.Breve))
        basic.pause(1000)
    }
})
```
 
 
```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
