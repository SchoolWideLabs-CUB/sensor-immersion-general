# Display Magnetic Strength
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:00655-59254-99094-06158 -->

## Welcome

We are going write a program to display the strength of the magnetic field on your micro:bit.

## Step 2

To start, use the ``||basic:show number||`` (Basic) command to display any number.

#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!

## Step 3

Now change the value of the number shown to be the ``||input:strength||`` of the ``||input:magnetic force||`` (Input:more).

## Step 4

What is the difference between putting this command in the block for ``||basic:on start||`` (Basic), the block ``||basic:forever||`` (Basic), or the block ``||input:on button A pressed||`` (Input)?

If you get the message "tilt to fill screen" and need help, [read this page or watch the video here.](https://support.microbit.org/support/solutions/articles/19000008874-calibrating-the-micro-bit-compass#:~:text=When%20you%20load%20a%20program,this%2C%20your%20program%20will%20run.)

## Step 5

Congratulations, you're done!

```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.magneticForce(Dimension.Strength))
})
```
