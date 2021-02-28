# graph soil moisture tutorial
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gatorSoil to display soil moisture values as a graph on your micro:bit
 
Submit your final code to your teacher on schoology (or wherever your teacher asks)
  
## Step 2
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
To start, use the ``||led:plot bar graph||`` command to display a number as a graph on your micro:bit led screen
 
#### ~ tutorialhint
Try clicking on the 'Led' drawer to find the block you need!
 
```blocks
basic.forever(function () {
    led.plotBarGraph(
    0,
    0
    )
})
 
```
 
## Step 3
 
Now change the value being graphed to be the sound with ``||gator:soil moisture||`` 
 
You should have the signal come from the pin on P2 and the power come from the pin on P1
 
#### ~ tutorialhint
 
```blocks
basic.forever(function () {
    led.plotBarGraph(
    gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1),
    0
    )
})
 
```   
 
## step 4 
 
Finally, you need to specify the value that is the top of the graph (y-axis). The wettest reading does not go over 0.75, so let’s make that value 0.75
 
 
### ~ tutorialhint
```blocks
basic.forever(function () {
    led.plotBarGraph(
    gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1),
    0.75
    )
})
 
```
 
## step 5
Great! You did it. Now you can test it out. Does the graph change as the moisture changes? What happens if you change the `||led.up to||`` value for the ``||led.plotBarGraph||`` ?
 
 
```ghost
basic.forever(function () {
    led.plotBarGraph(
    gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1),
    0.75
    )
})
 
if (0 * 0 == 0 + 0) {
    
}
 
```
 
```package
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
