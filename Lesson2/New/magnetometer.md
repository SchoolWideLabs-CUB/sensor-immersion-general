# Display Magnetic Strength
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:18059-03779-14064-65014 -->

## Welcome

We are going to write a program to show the strength of the magnetic field measured by your micro:bit.

## Step 1

To start, use the ``||basic:show number||`` (Basic) block to display any number by placing it inside the ``||basic:on start||`` (Basic) event.

#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!

```blocks
basic.showNumber(0)
```

## Step 3

Now change the value of ``||basic:show number||`` (Basic) to be the ``||input:strength||`` of the magnetic field by replacing your number with ``||input:magnetic force||`` (Input:more).

#### ~ tutorialhint
```blocks
basic.showNumber(input.magneticForce(Dimension.Strength))
```

## Step 4

What is the difference between putting this command in the ``||Basic: on start||`` (Basic) event, the ``||Basic: forever||`` (Basic) event, or the ``||Input: on button A pressed||`` (Input) event?

Try them out!

If you get the message "tilt to fill screen", you just need to orient the sensor by tilting the micro:bit until the screen is full. If you are having issues, [read this page or watch the video here.](https://support.microbit.org/support/solutions/articles/19000008874-calibrating-the-micro-bit-compass#:~:text=When%20you%20load%20a%20program,this%2C%20your%20program%20will%20run.)

## Step 5

Congratulations, you're done!

#### ~ tutorialhint
This is what one correct answer looks like:
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.magneticForce(Dimension.Strength))
    })
```

```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.magneticForce(Dimension.Strength))
})
```
