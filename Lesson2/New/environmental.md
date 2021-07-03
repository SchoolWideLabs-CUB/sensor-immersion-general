# Collecting Temperature Data with the Environmental Sensor
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:78222-05534-05239-30450 -->

## Step 1

We are going to learn how to use a micro:bit and gator:bit environmental sensor to display temperature values.

```template
input.onButtonPressed(Button.A, function () {

})
```

## Step 2

If you need help with wiring, take a look at [this guide](https://drive.google.com/file/d/1bxYGD53_5G7AXUVdqf0oQRN7OQ0Bnc9e/view?usp=sharing).

## Step 3

To start, use the ``||gatorEnvironment: initialize sensors||`` (GatorEnvironment) command to turn the sensor on.

Start the sensor when the micro:bit powers on, inside the ``||basic:on start||`` (Basic) block.

## Step 4

Use the ``||basic:show number||`` (Basic) block to show a value on the micro:bit's led screen when ``||input:button A is pressed||`` (Input). It can be any number you want!

## Step 5

Next, let's replace your number with the temperature from the sensor. Using the ``||gatorEnvironment:get value||`` (GatorEnvironment) command inside the ``||basic:show number||`` (Basic) block will show the temperature on the micro:bit.

#### ~ tutorialhint

Watch out, there are two different ways to read the temperature. DegreesF will return Fahrenheit, while degreesC will return in Celsius!

## Step 6

That number looks ugly, let's clean it up. To round to the nearest whole number, we can use the ``||Math: round||`` (Math) command. This will show the temperature as a whole number, much better!

#### ~ tutorialhint

Rounding makes the value easier to read on the display.

Instead of seeing 72.9999999999, you just see 73.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})

```

## Step 5
Great, you did it!

Now you can test it out. How could you use the Math blocks to change the display to two times the temperature? Would you round before or after you double the temperature?


```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF) * 2))
})
gatorEnvironment.beginEnvironment()
```

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
