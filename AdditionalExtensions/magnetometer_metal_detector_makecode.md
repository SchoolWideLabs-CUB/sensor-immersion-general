# Metal Detector
### @explicitHints true
 
## Welcome
 
We are going write a program to help you find metal objects, your microbit will become a metal detector
 
Submit your answers using this google form with your teacher's name that ends with "Metal Detector"
 
https://schoolwidelabs.github.io/sensor-immersion/ 
 
```template
input.onButtonPressed(Button.A, function () {
})
```
 
## before you begin
 
Answer question 1 on the google form, describing your plans for how to get the micro:bit to tell you about close it is to a metal (magnetic) object
 
## Step 2
 
To start, want to use a ``||logic.if||`` command to do something in response to something else
 
#### ~ tutorialhint
Make sure your ``||logic.if||`` is inside the ``||input.onButtonPressed||`` command
 
```blocks
input.onButtonPressed(Button.A, function () {
    if (true) {
        
    }
})
```
 
## Step 3
We need to use a ``||logic.>||`` command to do something if the ``||input.magneticForce||`` is greater than 250
 
#### ~ tutorialhint
Make sure your ``||logic.>||`` is facing the magneticForce value and away from the 250 that you typed
 
```blocks
input.onButtonPressed(Button.A, function () {
    if (input.magneticForce(Dimension.Strength) > 250) {
        
    }
})
```
## Step 4
**In the Google Form**, answer: What would happen if you changed the 250 to 100? 
 
 
## Step 5
We want the metal detector to sound if it senses a strong magnet that is over 250
 
Use the ``||music.playTone||`` command to play a tone if the ``||input.magneticForce||`` is over 250
 
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    if (input.magneticForce(Dimension.X) >= 250) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    }
})
```
## Step 6
We also want the metal detector to also tell us the value of the ``||input.magneticForce||``, add that after the ``||logic.if||`` command
 
#### ~ tutorialhint
The ``||math.round||`` command rounds the displayed value to the nearest whole number
 
```blocks
input.onButtonPressed(Button.B, function () {
    if (input.magneticForce(Dimension.X) >= 250) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    }
    basic.showNumber(Math.round(input.magneticForce(Dimension.Strength)))
})
```
## Step 7
 
Use the ``||led.setBrightness||`` and ``||basic.showIcon||`` commands before the ``||locic.if||`` command to display a shape of your choice based on how strong the ``||input.magneticForce||`` is
 
## Step 8
 
When you are done, **put your answer and a screenshot of your final code in the google form**
 
Congratulations, you're done!
 
**Fill out the final question in the google form**
 
#### ~ tutorialhint
This is what one correct answer looks like:
```blocks
input.onButtonPressed(Button.A, function () {
    led.setBrightness(input.magneticForce(Dimension.Strength))
    basic.showIcon(IconNames.Square)
    if (input.magneticForce(Dimension.Strength) > 250) {
        music.playTone(659, music.beat(BeatFraction.Whole))
    }
    basic.showNumber(Math.round(input.magneticForce(Dimension.Strength)))
})
```
 
```ghost
input.onButtonPressed(Button.A, function () {
    led.setBrightness(input.magneticForce(Dimension.Strength))
    basic.showIcon(IconNames.Square)
    if (input.magneticForce(Dimension.Strength) > 250) {
        music.playTone(659, music.beat(BeatFraction.Whole))
    }
    basic.showNumber(Math.round(input.magneticForce(Dimension.Strength)))
})
```
    