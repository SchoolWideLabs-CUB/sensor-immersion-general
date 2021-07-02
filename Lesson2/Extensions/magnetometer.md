# Display Magnetic Strength
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:87862-64181-20939-94348 -->

## Welcome

We are going write a program to display the strength of the magnetic field on your micro:bit.

```template
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.magneticForce(Dimension.X))
})
```

## Step 2

To start, we have provided the final code from the Show Magnet Strength Tutorial from Lesson 2.

## Step 3

Now before we are going to add the display for the other magnetic strengths, we should label this one so we know what reading we are getting. Above the ``||basic:show number||`` (Basic) command, add a ``||basic:show string||`` (Basic) command and have it show 'X' so you know that you are seeing the magnetic force in the X direction.

## Step 4

Great! Now make a similar block to show magnetic force for the other readings, but with different ``||input:Inputs||`` (Input) triggering the micro:bit to show different directions of magnetic forces. Make sure you use ``||basic:show string||`` (Basic) to label them so you know what readings are being displayed.

#### ~ tutorialhint
This is what one correct answer looks like (yours may be different, there are many correct answers here):
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.magneticForce(Dimension.X))
})
input.onButtonPressed(Button.AB, function () {
    basic.showNumber(input.magneticForce(Dimension.Z))
})
input.onButtonPressed(Button.B, function () {
    basic.showNumber(input.magneticForce(Dimension.Y))
})
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(input.magneticForce(Dimension.Strength))
})
```
## Step 5

Now you are done! Experiment with how the magnetic field is different in different directions and feel free to add ``||math:rounding||`` (Math).

If you get the message “tilt to fill screen” and need help, [read this page or watch the video here.](https://support.microbit.org/support/solutions/articles/19000008874-calibrating-the-micro-bit-compass#:~:text=When%20you%20load%20a%20program,this%2C%20your%20program%20will%20run.)


```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(input.magneticForce(Dimension.Strength)))
})
```
