# show Temperature CO2 and Humidity Data with the Environmental Sensor
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gator:bit environmental sensor  to display temperature, CO2 and humidity values based on different inputs
 
Submit your final code to your teacher on schoology (or wherever your teacher asks)
  
```template
input.onButtonPressed(Button.A, function () {
    
})
```
  
## Step 2
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
To start, use the GatorEnvironment ``||gatorEnvironment: initialize||`` command start the sensor when the ``||basic: program starts||``
 
 
## Step 3
 
Use the ``||basic:showNumber||`` and ``||gatorEnvironment.GatorEnvironment.get||`` commands to show the temperature on the micro:bit. Make sure to ``||Math: round||`` 
so you can read the number on the micro:bit. 
 
#### ~ tutorialhint
 
Rounding makes the value easier to read on the display. 
Instead of seeing 72.9999999999, you just see 73.
 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
 
```
 
## Step 4
 
Now before we are going to add the display for the other sensors, we should label this one so we know what reading we are getting. Above the ``||basic:showNumber||`` command, add a ``||basic:showString||`` command and have it say “Temp” so you know that you are seeing the temperature.
 
#### ~ tutorialhint
 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("Temp")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
 
```
 
## Step 5
Great! Now repeat steps 3 and 4 but have different inputs trigger the microbit showing different environmental data like humidity and CO2. Make sure you use ``||basic:showString||``to label them so you know what readings are being displayed
 
#### ~ tutorialhint
It could look like this, there are many correct answers 
input.onButtonPressed(Button.A, function () {
    basic.showString("Temp")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
input.onButtonPressed(Button.B, function () {
    basic.showString("Humidity")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
})
input.onGesture(Gesture.Shake, function () {
    basic.showString("CO2")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.eCO2)))
})
gatorEnvironment.beginEnvironment()
 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showString("Temp")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
input.onButtonPressed(Button.B, function () {
    basic.showString("Humidity")
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.humidity))
})
input.onGesture(Gesture.Shake, function () {
    basic.showString("CO2")
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.eCO2))
})
gatorEnvironment.beginEnvironment()
if (0 * 0 == 0 + 0) {}
```
 
 
```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
