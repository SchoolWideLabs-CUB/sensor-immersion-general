# Collecting Temperature Data with the Environmental Sensor
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:83973-76377-64692-21982 -->

## Step 1

We are going to learn how to use a micro:bit and gator:bit environmental sensor to display temperature values.

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/1bxYGD53_5G7AXUVdqf0oQRN7OQ0Bnc9e/view?usp=sharing)

## Step 2

To start, use the ``||gatorEnvironment: initialize sensors||`` (GatorEnvionment) command, turn on the sensors when the program starts using the ``||basic:on start||`` (Basic) block.

## Step 3

Use the ``||basic: show number||`` (Basic) and ``||gatorEnvironment: get value||`` (GatorEnvionment) blocks to show the temperature on the micro:bit. Make sure to ``||math:round||`` (Math) so you can read the number cleanly on the micro:bit.


#### ~ tutorialhint

Rounding makes the value easier to read on the display.
Instead of seeing 72.9999999999, you just see 73.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})

```

## Step 4
Great! You did it. Now you can test it out. How could you use the Math buttons to change the display to two times the temperature? Would you round before or after you double the temperature?

```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF) * 2))
})
gatorEnvironment.beginEnvironment()
```

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
