# Show Soil Moisture Tutorial
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:66111-97773-95597-06119 -->

## Step 1

We are going to learn how to use a micro:bit and GatorSoil to display soil moisture values.

```template
input.onButtonPressed(Button.A, function () {

})
```

## Step 2

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/18e1Yyj8VSsILIePJkI6tx6cDbjrS48s8/view?usp=sharing)

## Step 3

To start, use the ``||basic:show number||`` (Basic) command to display any number when ``||input:button A is pressed||`` (Input).

#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!

```blocks
input.onButtonPressed(Button.A, function () {basic.showNumber(0)}
```

## Step 3

Now change the value of ``||basic:show number||`` to be the soil moisture with the ``||gator:get moisture||`` (GatorSoil) command.

You should have the signal come from the pin on P2 and the power come from the pin on P1.

#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```

## step 4
Great, you did it!

Now you can test it out. How could you use the Math buttons to change the display to show bigger values than 1?

### ~ tutorialhint
Think about getting a percentage moisture by multiplying the value from the sensor by 100 before you round it.
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```




```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1)))
})
if (0 * 0 == 0 + 0) {

}

```

```package
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
