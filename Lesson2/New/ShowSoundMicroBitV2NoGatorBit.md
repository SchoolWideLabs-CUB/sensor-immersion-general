# Show Sound Tutorial microbit v2 without gator:bit
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:35035-43801-27844-14928 -->

## Step 1

We are going to learn how to use a micro:bit v2 to show how loud it is in the room.

```template
input.onButtonPressed(Button.A, function () {

})
```

## Step 2

To start, use the ``||basic:show number||`` (Basic) block to show any number when ``||input:button A is pressed||`` (Input). Pick whatever number you want!

#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!

```blocks
input.onButtonPressed(Button.A, function () {
	basic.showNumber(0)
})
```

## Step 3

Now change the number shown in ``||basic:show number||`` (Basic) to be the sound with ``||input:sound level||``.

Make sure it snaps into the right place! We want it to replace the number you chose in the last step.

#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.soundLevel())
})
```

## step 4

Last, let's get rid of that decimal!

To round to the nearest whole number, you can use the ``||math.round||`` (Math) oval block. To do this, move the ``||input:sound intensity||`` inside of the ``||Math:round||`` oval, and put that into the ``||basic:show number||`` (Basic) block.

That's better!

### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(input.soundLevel()))
})
```

## step 5
Great, you did it!

```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(input.soundLevel()))
})
if (0 * 0 == 0 + 0) {

}

```

```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
```
