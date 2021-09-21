# Show Sound Tutorial
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:69540-64120-84994-08338 -->

## Step 1

We are going to learn how to use a micro:bit and gator:microphone to show how loud it is in the room.

```template
input.onButtonPressed(Button.A, function () {

})
```

## Step 2

First, we need to wire the gator:microphone to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/1oiQ0SdTL-UBnaFOiDmDOU_auGtIwzq84lymv9pf5Y0E/edit?usp=sharing)

## Step 3

To start, use the ``||basic:show number||`` (Basic) block to show any number when ``||input:button A is pressed||`` (Input). Pick whatever number you want!

#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!

```blocks
input.onButtonPressed(Button.A, function () {
	basic.showNumber(0)
})
```

## Step 4

Now change the number shown in ``||basic:show number||`` (Basic) to be the sound with ``||gatorMicrophone:sound intensity||`` (GatorMicrophone).

Make sure it snaps into the right place! We want it to replace the number you chose in the last step.

#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorMicrophone.getSoundIntensity())
})
```

## step 5

Last, let's get rid of that decimal!

To round to the nearest whole number, you can use the ``||math.round||`` (Math) oval block. To do this, move the ``||gatorMicrophone:sound intensity||`` inside of the ``||Math:round||`` oval, and put that into the ``||basic:show number||`` (Basic) block.

That's better!

### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity())
})
```

## step 6
Great, you did it!

Now you can test it out. How could you use the ``||math:Math||`` oval blocks to change the display to show a one or two digit number for the sound you are measuring?


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
