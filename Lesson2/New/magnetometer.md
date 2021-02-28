# Display Magnetic Strength
### @explicitHints true
 
## Welcome
 
We are going write a program to display the strength of the magnetic field on your micro:bit
 
## Step 1
 
To start, use the ``||basic:show number||`` command to display any number
 
#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!
 
```blocks
basic.showNumber(0)
```
 
## Step 3
 
Now change the value of ``||basic:showNumber||`` to be the strength of the magnetic field with ``||input:magneticForce||`` 
 
Do you use the magnetic force of "x", "y", "z" or "strength"? 
 
#### ~ tutorialhint
```blocks
basic.showNumber(input.magneticForce(Dimension.Strength))
```
 
## Step 4
 
What is the difference between putting this command in the block for ``||Basic: on start||``, the block ``||Basic: forever||``, or ``||Input: on button A pressed||``?
 
If you get the message "tilt to fill screen" and need help, [read this page or watch the video here.](https://support.microbit.org/support/solutions/articles/19000008874-calibrating-the-micro-bit-compass#:~:text=When%20you%20load%20a%20program,this%2C%20your%20program%20will%20run.)
 
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

    
