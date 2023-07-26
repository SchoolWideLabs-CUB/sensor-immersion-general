# Graph Soil Moisture Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:46806-59054-49994-14601 -->

## Step 1

We are going to learn how to use a micro:bit and gator:soil to show the soil moisture values as a graph on your micro:bit!

```template
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, gatorSoilType.soilMoisture, DigitalPin.P1))
})
```

## Step 2

First, make sure your gator:soil is still wired correctly to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/12oWXe1Icgzu3zD3qE00i4QrkLfok5Tlvc9vSgI2yB3g/edit?usp=sharing)

To start, remove the ``||basic:show number||`` (Basic) block and use the ``||led:plot bar graph||`` (Led) block to display any number as a graph on your micro:bit led screen.

#### ~ tutorialhint
Try clicking on the 'Led' drawer to find the block you need, you can make up the numbers!

```blocks
basic.forever(function () {
    led.plotBarGraph(
    0,
    0
    )
})

```

## Step 3

This ``||led:plot bar graph||`` (Led) block takes in two oval blocks. The first is the value we want to graph, usually an oval block from a sensor (like our ``||gatorSoil:get moisture||``!).

Now change the value being graphed to be the value from the sensor, using the ``||gatorSoil:get moisture||`` (GatorSoil) block.

You should have the signal come from the pin on P2 and the power come from the pin on P1.

#### ~ tutorialhint

```blocks
basic.forever(function () {
    led.plotBarGraph(
    gatorSoil.moisture(AnalogPin.P2, gatorSoilType.soilMoisture, DigitalPin.P1),
    0
    )
})

```   

## step 4

The second oval in the ``||led:plot bar graph||`` (Led) block is the maximum value of our graph.

The wettest reading does not go over 0.75, so let’s make that value 0.75.


### ~ tutorialhint
```blocks
basic.forever(function () {
    led.plotBarGraph(
    gatorSoil.moisture(AnalogPin.P2, gatorSoilType.soilMoisture DigitalPin.P1),
    0.75
    )
})

```

## step 5
Great, you did it!

Now you can test it out. Does the graph change as the moisture changes? What happens if you change the second oval for the ``||led.plot bar graph||`` (Led)?

If it does not work, see the hint for a few common issues!

#### ~ tutorialhint
Here are some common issues and their solutions:
1. Check for two red lights next to the 3.3V pin on the gator:bit. If they are off, check the following switch and make sure it is on.
![VOut](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/VOUT_Switch.jpg?raw=true)

2. Double check that your P# values and your wiring matches up! The first value in the block (P2) should match the green wire, the second value (P1) should match the red wire. Also, do not set the power pin (red wire) as P0, it will not work.
![Soil Block](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/gatorsoil_get_block.PNG?raw=true)

3. Otherwise, double check your wiring with the wiring guide [here](https://docs.google.com/document/d/12oWXe1Icgzu3zD3qE00i4QrkLfok5Tlvc9vSgI2yB3g/edit?usp=sharing).



```ghost
basic.forever(function () {
    led.plotBarGraph(
    gatorSoil.moisture(AnalogPin.P2, gatorSoilType.soilMoisture DigitalPin.P1),
    0.75
    )
})

if (0 * 0 == 0 + 0) {

}

```

```package
gatorSoil=github:sparkfun/pxt-gator-soil
```
