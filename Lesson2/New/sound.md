# Show Sound Tutorial
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:06304-43514-59374-85191 -->

## Step 1

We are going to learn how to use a micro:bit and GatorMicrophone to display sound values.

```template
input.onButtonPressed(Button.A, function () {

})
```

## Step 2

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/1cG0KVRXibqE1kTGMskL4cwI-tukBHXyh/view?usp=sharing)

## Step 3

To start, use the ``||basic:show number||`` (Basic) command to display any number when ``||input:button A is pressed||`` (Input).

#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!

```blocks
input.onButtonPressed(Button.A, function () {
	basic.showNumber(0)
})
```

## Step 4

Now change the number shown in ``||basic:show number||`` (Basic) to be the sound with ``||gatorMicrophone:sound intensity||`` (GatorMicrophone).

#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorMicrophone.getSoundIntensity())
})
```

## step 5

Last, let's get rid of that decimal!

To round to the nearest whole number, you can use the ``||math.round||`` (Math) command.

Use this command to change the displayed value to be the ``||gatorMicrophone:sound intensity||`` (GatorMicrophone) rounded to the nearest whole number.

### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity())
})
```

## step 6
Great, you did it!

Now you can test it out. How could you use the ``||math:Math||`` buttons to change the display to show a one or two digit number for normal sound inputs?


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
