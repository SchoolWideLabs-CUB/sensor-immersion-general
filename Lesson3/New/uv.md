#sound an alarm when the uv level get above a certain threshold
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gator:bit uv sensor to sound an alarm if the uv level gets too high

## Step 2
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
To start, use the GatorUV ``||gatorUV: initialize||`` command start the sensor when the ``||basic: program starts||``
 
 
## Step 3
 
First we need to 'calibrate' the sensor to find what values of UV light are above normal and should sound the alarm. Use your skills from Lesson 2 to determine the current UV level in the room. 
 
 
#### ~ tutorialhint
 
You are going to need to make a temporary program or use an old program (from Lesson 2) that has the ``||basic:Show Value||`` and ``||gatorUV: get UVA value||`` commands. 
 
## Step 4
 
Now that you know what the UV level is in the room, pick a number that is higher than it. We are going to program the alarm to sound if the UV level goes above this value.  
  
## Step 5
 
We need to set a logic command to test if the measured UV level is below your selected 'alarm value'. Use the ``||gatorUV: get UVA value||`` and ``||logic. 0 < 0 ||`` commands to write this logic statement for when the observed UV level value is less than (<) your 'alarm value'. 
 
#### ~ tutorialhint
Remember that order matters, the get UVA value needs to be on the pointy side and the 'alarm value' needs to be on the side where the < opens towards. 

 
## Step 6
 
Now that we have the 'alarm value' logic, it is time to make an if statement to tell the microbit what to do when the values are BELOW this value... that is, when the alarm is not going off.
 
Use the forever, ``||basic:Show Icon||``, ``||basic:Pause||`` and ``||logic:If Else||`` and commands to determine what happens when the UV level observed is below the alarm value. Adding a pause after you show the icon keeps it from going too fast. 
 
#### ~ tutorialhint
It will look like this, although you may have an 'alarm value' other than 1000
```blocks
basic.forever(function () {
    if (gatorUV.UV() < 1000) {
        basic.showIcon(IconNames.Happy)
        basic.pause(1000)
    } else {
    	
    }
})
```
 
## Step 7
 
The final step is to tell the microbit what to do if the observed UV level value is NOT below your 'alarm value'. This goes in the 'else' part of the ``||logic:If Else||`` command. 
 
We recommend you have a ``||basic:Show Icon||``, ``||music:play tone||`` and ``||basic:Pause||`` commands in that order. Also, the icon should be different from when the alarm is not going off. 
 
## Step 8
 
Congratulations, you're done!
 
 
#### ~ tutorialhint
 
Here is one example of what it could look like:
 
```blocks
gatorUV.begin()
basic.forever(function () {
    if (gatorUV.UV() <= 2000) {
        basic.showIcon(IconNames.Happy)
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Sad)
        music.playTone(554, music.beat(BeatFraction.Breve))
        basic.pause(1000)
    }
})
```
 
```ghost
input.onButtonPressed(Button.A, function () {  basic.showNumber(Math.round(gatorUV.UV()))
})
gatorUV.begin()
basic.forever(function () {
    if (gatorUV.UV() <= 2000) {
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
gatorUV=github:sparkfun/pxt-gator-UV#v0.1.2
```
