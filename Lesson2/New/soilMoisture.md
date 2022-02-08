# Show Soil Moisture Tutorial
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:88143-50646-27932-08120 -->

## Step 1

We are going to learn how to use a micro:bit and gator:soil sensor to show the moisture level of some soil.

```template
input.onButtonPressed(Button.A, function () {

})
```

## Step 2

First, we need to wire the gator:soil sensor to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/12oWXe1Icgzu3zD3qE00i4QrkLfok5Tlvc9vSgI2yB3g/edit?usp=sharing)

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

If it does not work, see the hint for a few common issues!

#### ~ tutorialhint
Here are some common issues and their solutions:
1. Check for two red lights next to the 3.3V pin on the gator:bit. If they are off, check the following switch and make sure it is on.
![VOut](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/VOUT_Switch.jpg?raw=true)

2. If the speaker is not making any noise, check this switch and make sure it is on:
![Speaker](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/SPEAKER_Switch.jpg?raw=true)

3. Otherwise, double check your wiring with the wiring guide [here](https://docs.google.com/document/d/12oWXe1Icgzu3zD3qE00i4QrkLfok5Tlvc9vSgI2yB3g/edit?usp=sharing).




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
