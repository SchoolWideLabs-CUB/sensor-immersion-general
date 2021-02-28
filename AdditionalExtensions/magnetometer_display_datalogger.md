# magnetometer_display_datalogger
# display magnetic field data logger simulator
### @explicitHints true
 
## Welcome
 
We are going to learn how to use a micro:bit to collect data on the magnetic force that you can see on your computer screen.
 
Submit your answers using the google form under your teacher's name titled "magnetic field radio data logger simulator"
 
https://schoolwidelabs.github.io/sensor-immersion-google-forms
 
```template
basic.forever(function () {
})
```
 
## before you begin
 
**Answer question 1 on the google form**
 
Why would we want to display and collect the data we from a sensor on the computer instead of just showing the numbers on the micro:bit?
 
## Step 3
 
Use the ``||basic.forever||`` and ``||serial.serial write Value||`` commands to send magneticForce strength to the computer through the USB port 

Did you know that the S in USB is the word Serial?
 
#### ~ tutorialhint
rounding is optional but helpful
```blocks
basic.forever(function ()  {
    serial.writeValue("x", Math.round(input.magneticForce(Dimension.Strength))))
})
```
 
## step 4 
Name your variable by changing the x to a name that describes what the values represent
 
## step 5
Use the ``||basic.pause||`` command to add in a half second (500ms) pause so the data comes in a little slower
 
### ~ tutorialhint
```blocks
basic.forever(function () {
    serial.writeValue("magnetic strenght", Math.round(input.magneticForce(Dimension.Strength)))
    basic.pause(500)
})
```
 
## step 6
Great! You did it. Now you can test it out. If it gets stuck, try hitting the refresh icon to restart the simulator and then click "show console" to see the data
 
**Don't forget to fill out the final questions on the google form.**
 
```ghost
basic.forever(function () {
    serial.writeValue("magnetic strenght", Math.round(input.magneticForce(Dimension.Strength)))
    basic.pause(500)
})
```
