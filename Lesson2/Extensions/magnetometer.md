# Display Magnetic Strength In All Directions
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:65673-32947-10790-55062 -->

## Welcome

We are going to write a program to display the measured magnetic force in different directions on your micro:bit.

```template
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.magneticForce(Dimension.X))
})
```

## Step 2

To start, below is the final code from the Display Magnet Strength Tutorial from Lesson 2. If you haven't done that one, start there.

## Step 3

Right now, we have one direction (the x direction) already displaying. Because we are going to add the other directions, we should label this one so we know what reading we are getting.

Above the ``||basic:show number||`` (Basic) block, add a ``||basic:show string||`` (Basic) block and have it show 'X' so you know that you are seeing the magnetic force in the x direction.

## Step 4

Great! Now make similar blocks to show magnetic force for the other readings, but with different ``||input:Input||`` (Input) events. Explore the ``||input:Input||`` drawer to see what other events you can use! Events are the blocks that are designed to hold others, like the ``||input:on button A pressed||`` event.

Make sure you use the ``||basic:show string||`` (Basic) block to label them so you know what readings are being displayed.

#### ~ tutorialhint
This is what one correct answer looks like (yours may be different, there are many correct answers here):
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString('X')
    basic.showNumber(input.magneticForce(Dimension.X))
})
input.onButtonPressed(Button.AB, function () {
    basic.showString('Z')
    basic.showNumber(input.magneticForce(Dimension.Z))
})
input.onButtonPressed(Button.B, function () {
    basic.showString('Y')
    basic.showNumber(input.magneticForce(Dimension.Y))
})
input.onGesture(Gesture.Shake, function () {
    basic.showString('Strength')
    basic.showNumber(input.magneticForce(Dimension.Strength))
})
```
## Step 5

Now you are done! Experiment with how the magnetic field is different in different directions.

If you get the message “tilt to fill screen” and need help, [read this page or watch the video here.](https://support.microbit.org/support/solutions/articles/19000008874-calibrating-the-micro-bit-compass#:~:text=When%20you%20load%20a%20program,this%2C%20your%20program%20will%20run.)


```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(input.magneticForce(Dimension.Strength)))
    basic.showString()
})
```
