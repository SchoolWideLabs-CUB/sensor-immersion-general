# Display Magnetic Strength
### @explicitHints true
 
## Welcome
  
We are going write a program to display the strength of the magnetic field on your micro:bit
 
Submit your final code to your teacher on schoology (or wherever your teacher asks)
 
  
```template
input.onButtonPressed(Button.A, function () {
    
})
```
 
## Step 2
 
To start, use the ``||basic:show number||`` command to display any number ``||input:when button A is pressed||``
 
#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!
 
```blocks
    input.onButtonPressed(Button.A, function () {
    basic.showNumber(0))
 
})
```
 
 
## Step 3
 
Now change the value of ``||basic:showNumber||`` to be the strength of the magnetic field with ``||input:magneticForce||`` in the x direction
 
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.magneticForce(Dimension.x)))
})
```
 
## Step 5
 
Great! Now repeat steps 3 and 4 but have different inputs trigger the microbit to show different directions of magnetic forces. Make sure you use ``||basic:showString||``to label them so you know what readings are being displayed
 
#### ~ tutorialhint
This is what one correct answer looks like:
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.magneticForce(Dimension.X))
})
input.onButtonPressed(Button.AB, function () {
    basic.showNumber(input.magneticForce(Dimension.Z))
})
input.onButtonPressed(Button.B, function () {
    basic.showNumber(input.magneticForce(Dimension.Y))
})
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(input.magneticForce(Dimension.Strength))
})
```
## Step 6
 
Now you are done! Experiment with how the magnetic field is different in different directions, feel free to add rounding
 
If you get the message “tilt to fill screen” and need help, [read this page or watch the video here.](https://support.microbit.org/support/solutions/articles/19000008874-calibrating-the-micro-bit-compass#:~:text=When%20you%20load%20a%20program,this%2C%20your%20program%20will%20run.)
 
 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(input.magneticForce(Dimension.Strength)))
})
```
