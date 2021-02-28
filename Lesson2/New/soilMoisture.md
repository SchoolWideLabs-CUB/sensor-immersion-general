# show soil moisture tutorial
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gatorSoil to display soil moisture values.
 
```template
input.onButtonPressed(Button.A, function () {
    
})
```
 
## Step 2
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
## Step 3
 
To start, use the ``||basic:show number||`` command to display any number when button a is pressed
 
#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!
 
```blocks
input.onButtonPressed(Button.A, function () {basic.showNumber(0)}
```
 
## Step 3
 
Now change the value of ``||basic:showNumber||`` to be the soil moisture with ``||gator:GetMoisture||`` 
 
You should have the signal come from the pin on P2 and the power come from the pin on P1
 
#### ~ tutorialhint
 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2))
})
```
 
## step 4 
 
In the ``||math.math||`` menu you will find the ``||math.round||`` command to round to the nearest whole number
 
Use this command to change the displayed value to be the soil moisture rounded to the nearest whole number. 
 
### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2)))
})
```
 
## step 5
Great! You did it. Now you can test it out. How could you use the Math buttons to change the display to show more detailed values than just 0 and 1?

### ~ tutorialhint
Think about getting a percentage moisture by multiplying the value from the sensor by 100 before you round it.
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2)*100))
})
```



 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2)))
})
if (0 * 0 == 0 + 0) {
    
}
 
```
 
```package
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
