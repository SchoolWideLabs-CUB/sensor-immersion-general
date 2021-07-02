# Display Sound Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:39331-22995-44625-11349 -->

## Step 1

We are going to learn how to use a micro:bit and GatorMicrophone to display sound values.

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/1cG0KVRXibqE1kTGMskL4cwI-tukBHXyh/view?usp=sharing)

## Step 2

To start, use the ``||basic:show number||`` (Basic) command to display any number ``||input:when button A pressed||`` (Input).

#### ~ tutorialhint
Try clicking on the 'Basic' and 'Input' drawers to find the blocks you need!

```blocks
input.onButtonPressed(Button.A, function () {basic.showNumber(0)}
```

## Step 3

Now change the value of the shown number to be the ``||gatorMicrophone:sound intensity||`` (GatorMicrophone).

## step 4

Wouldn't this look better as a whole number, not a decimal...

The ``||math.round||`` (Math) command can be used to round to the nearest whole number.

Use this command to change the displayed value to be the ``||gatorMicrophone:sound intensity||`` (GatorMicrophone) rounded to the nearest whole number.

### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity())
})
```

## step 5
Great! You did it. Now you can test it out. How could you use the math blocks to decrease the sound intensity output so the number displayed is smaller?

```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity()))
})
if (0 * 0 == 0 + 0) {

}

```

```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
```
