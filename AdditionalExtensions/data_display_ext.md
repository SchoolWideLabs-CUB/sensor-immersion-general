# Data Display Continued
### @explicitHints true

## Step 1
This is part of the program you created last time that shows the 
``||gatorEnvironment: temperature||`` when 
you press ``||input: button A||``, the ``||gatorEnvironment: humidity||``
when you press ``||input: button B||``, and the ``||gatorSoil: soil moisture||`` when
you press ``||input: button A and button B together||``. What if you wanted to change 
the program, so that you saw all three values: 
``||gatorEnvironment: temperature||``, ``||gatorEnvironment: humidity||``, 
and ``||gatorSoil: soil moisture||`` when you ``||input: pressed button A||``?
Change the code so that you see all three values when you press button A.

```template
input.onButtonPressed(Button.A, function () {
    Temp = Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF))
    basic.showNumber(Temp)
})

input.onButtonPressed(Button.B, function () {
    Humid = Math.round(gatorEnvironment.getMeasurement(measurementType.humidity))
    basic.showNumber(Humid)
})

input.onButtonPressed(Button.AB, function () {
    Soil_Moisture = Math.round(100 * gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
    basic.showNumber(Soil_Moisture)
})

gatorEnvironment.beginEnvironment()
let Temp = 0
Temp = 0
let Humid = 0
Humid = 0
let Soil_Moisture = 0
Soil_Moisture = 0
```

#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    Temp = Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF))
    basic.showNumber(Temp)
    Humid = Math.round(gatorEnvironment.getMeasurement(measurementType.humidity))
    basic.showNumber(Humid)
    Soil_Moisture = Math.round(100 * gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
    basic.showNumber(Soil_Moisture)
})
```

## Step 2
Without looking at the code, how would someone know what value the micro:bit is showing?
Could you use some ``||basic: basic blocks||`` to label the values?

#### ~ tutorialhint
You can use the ``||basic: show string||`` block to label what you are looking at.
If the numbers are going too fast, you can use the ``||basic: pause||`` block between
values.

## Step 3
``|Download|`` the code and try it out. 

```ghost
basic.showString("Temp")
basic.pause(1000)
```
    

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
