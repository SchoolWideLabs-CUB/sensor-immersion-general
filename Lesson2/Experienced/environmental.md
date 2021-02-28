# Collecting Temperature Data with the Environmental Sensor
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gator:bit environmental sensor  to display temperature values
 
Submit your answers using the google form linked on [this page](https://schoolwidelabs.github.io/sensor-immersion/assessments/Lesson2/environmental_assessment.html) under your teacher's name.
 
 
## Step 2
 
**Before you begin, answer question 1 on the google form**
 
Describe your plan for getting the microbit to display the temperature values
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
## Step 3
 
To start, use the GatorEnvironment initialize command start the sensor when the program starts
  
## Step 4
 
Use the show number and gator environment “get” commands to show the temperature on the micro:bit. Make sure to round so you can read the number on the micro:bit.
 
 
#### ~ tutorialhint
 
Rounding makes the value easier to read on the display. 
Instead of seeing 72.9999999999, you just see 73.
 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
 
```
 
## Step 5
Great! You did it. Now you can test it out. How could you use the Math buttons to change the display to two times the temperature? Would you round before or after you double the temperature?
 
**Don't forget to fill out the final questions on the google form.**
 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF) * 2))
})
gatorEnvironment.beginEnvironment()
```
 
```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
