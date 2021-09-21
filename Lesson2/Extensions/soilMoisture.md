# Graph Soil Moisture Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:56835-39106-97817-82671 -->

## Step 1

We are going to learn how to use a micro:bit and gator:soil to show the soil moisture values as a graph on your micro:bit!

```template
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
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
    gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1),
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
    gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1),
    0.75
    )
})

```

## step 5
Great, you did it!

Now you can test it out. Does the graph change as the moisture changes? What happens if you change the second oval for the ``||led.plot bar graph||`` (Led)?


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
