# Show Soil Moisture Tutorial
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:29130-81776-52221-23349 -->

## Step 1

We are going to learn how to use a micro:bit and gator:soil sensor to show the moisture level of some soil.

```template
input.onButtonPressed(Button.A, function () {

})
```

## Step 2

First, we need to wire the gator:soil sensor to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/18e1Yyj8VSsILIePJkI6tx6cDbjrS48s8/view?usp=sharing)

## Step 3

To start, use the ``||basic:show number||`` (Basic) block to display any number when ``||input:button A is pressed||`` (Input).

Choose whatever number you want!

#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!

```blocks
input.onButtonPressed(Button.A, function () {basic.showNumber(0)}
```

## Step 3

Now change your value in ``||basic:show number||`` to be the soil moisture with the ``||gator:get moisture||`` (GatorSoil) oval block.

You should have the signal come from the pin on P2 and the power come from the pin on P1.

This oval block is tricky, so double check and make sure that your green wire goes to P2, your red wire goes to P1, and that they are in that order in the oval block.

#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```

## step 4
Great, you did it!

Now you can test it out, the value you will see is a percentage between 0 and 1.

How can we use the ``||Math:Math||`` oval blocks to make this a real percentage, between 0 and 100?

### ~ tutorialhint
Think about getting a percentage moisture by multiplying the value from the sensor by 100 before you round it.
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1) * 100)
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
