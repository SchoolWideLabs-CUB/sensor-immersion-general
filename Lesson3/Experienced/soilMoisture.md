# sound an alarm if soil moisture drops below a certain threshold
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gator:bit soil moisture sensor  to sound an alarm if the soil gets too dry
 
Submit your answers using the google form linked on [this page](https://schoolwidelabs.github.io/sensor-immersion/assessments/Lesson3/soil_moisture_assessment.html) under your teacher's name. 
 
  
## Step 2
 
When wiring the soil sensor, you should have the signal wire go from the SIG pin on the sensor to the port labeled P2 on the gator:bit. The power should go from the 3V3 pin on the sensor to the pin labeled P1 on the gator:bit. 
 
#### ~ tutorialhint
 
![Soil Wiring](https://schoolwidelabs.github.io/sensor-immersion/images/soil_diagram.png)
 
## Step 3
 
First we need to ‘calibrate’ the sensor to find the ‘alarm value’ for soil moisture that is considered too dry. Values above this will sound the alarm. Use your skills from Lesson 2 to determine what the sensor reads for wet and dry soil. If you do not have plants or soil to test with, use a cup of water for wet soil and the air for dry soil. 
 
**Enter these values on questions 2 and 3 on the google form**
 
#### ~ tutorialhint
 
You are going to need to make a temporary program or use an old program (from Lesson 2) that has the ‘show value’ and gator soil ‘get’ commands. 
 
## Step 4
 
We need to set a logic command to test if the measured soil moisture is below your selected ‘alarm value’. Use the gator soil ‘get’ and ‘ 0 < 0 ‘  commands to write this logic statement for when the observed soil moisture is less than (<) your ‘alarm value’. 
 
Note that you may need to flip the < to a < depending on where you put the ‘get moisture’ command
 
#### ~ tutorialhint
Remember that order matters, the ‘alarm value’ needs to be on the pointy side and the get soil moisture needs to be on the side where the < opens towards. 
 

![Alarm Value Logic2](https://schoolwidelabs.github.io/sensor-immersion/images/soil_code.png)
 
## Step 5
 
Now that we have the ‘alarm value’ logic, it is time to make an if statement to tell the microbit what to do when the values are ABOVE this value... that is, when the alarm is not going off.
 
Use the forever, ‘Show Icon’, ‘Pause’ and ‘If Else” and commands to determine what happens when the soil moisture observed is above the alarm value. Adding a pause after you show the icon keeps it from going too fast. 
 
#### ~ tutorialhint
It will look like this, although you may have an ‘alarm value’ other than 0.5
```blocks
basic.forever(function () {
    if (gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2) > 0.5) {
        basic.showIcon(IconNames.Happy)
        basic.pause(1000)
    } else {
    	
    }
})
```
 
## Step 6
 
The final step is to tell the microbit what to do if the observed soil moisture value is NOT above your ‘alarm value’. This goes in the ‘else’ part of the ‘If Else’ command. 
 
We recommend you have a ‘show icon’, ‘play tone’ and ‘pause’ commands in that order. Also, the icon should be different from when the alarm is not going off. 
 
## Step 7
 
Congratulations, you're done!
 
**Fill out the final questions in the google form**
 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2)))
})
basic.forever(function () {
    if (gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2) > 0.5) {
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
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
