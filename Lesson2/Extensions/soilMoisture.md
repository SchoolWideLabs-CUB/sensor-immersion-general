# Graph Soil Moisture Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:61984-30477-01902-22350 -->

## Step 1

We are going to learn how to use a micro:bit and GatorSoil to display soil moisture values as a graph on your micro:bit.

```template
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P1, GatorSoilType.Moisture, DigitalPin.P2))
})
```

## Step 2

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/18e1Yyj8VSsILIePJkI6tx6cDbjrS48s8/view?usp=sharing)

To start, remove the ``||basic:show number||`` (Basic) block and use the ``||led:plot bar graph||`` (Led) command to display any number as a graph on your micro:bit led screen.

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

Now change the value being graphed to be the value from the sensor, using the ``||gatorSoil:soil moisture||`` (GatorSoil) block.

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

Finally, you need to specify the value that is the top of the graph (y-axis). The wettest reading does not go over 0.75, so let’s make that value 0.75.


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

Now you can test it out. Does the graph change as the moisture changes? What happens if you change the ``||led.up to||`` (Led) value for the ``||led.plot bar graph||`` (Led)?


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
