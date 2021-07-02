# Show Soil Moisture Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:40860-55455-71124-21687 -->

## Step 1

We are going to learn how to use a micro:bit and GatorSoil to display soil moisture values.

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/18e1Yyj8VSsILIePJkI6tx6cDbjrS48s8/view?usp=sharing)

## Step 2

To start, use the ``||basic:show number||`` (Basic) command to display any number ``||input:when button A pressed||`` (Input).

#### ~ tutorialhint
Try clicking on the 'Basic' and 'Input' drawers to find the blocks you need!

## Step 3

Now change the value of the number shown to be the ``||gatorSoil:soil moisture value||`` (GatorSoil).

You should have the signal come from the pin on P2 and the power come from the pin on P1.

#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```

## step 4
Great! You did it. Now you can test it out.

```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
if (0 * 0 == 0 + 0) {

}

```

```package
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
