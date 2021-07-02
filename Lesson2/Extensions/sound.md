# Graph Sound Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:70741-67010-40827-70008 -->

## Step 1

We are going to learn how to use a micro:bit and GatorMicrophone to display sound values as a graph on your micro:bit.

```template
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity())
})
```

## Step 2

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/1cG0KVRXibqE1kTGMskL4cwI-tukBHXyh/view?usp=sharing)

To start, remove the ``||basic:show number||`` (Basic) and use the ``||led:plot bar graph||`` (Led) command to display a number as a graph on your micro:bit led screen.

#### ~ tutorialhint
Try clicking on the 'Led' drawer to find the block you need, you can choose whatever numbers you want!

```blocks
basic.forever(function () {
    led.plotBarGraph(
    0,
    0
    )
})

```

## Step 3

Now change the value being graphed to be the sound with ``||gatorMicrophone:sound intensity||`` (GatorMicrophone).


#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorMicrophone.getSoundIntensity())
})
```   

## step 4

Finally, you need to specify the value that is the top of the graph (y-axis). Most sounds do not go over 2000, so let’s make that value 2000.


### ~ tutorialhint
```blocks
basic.forever(function () {
    led.plotBarGraph(
    gatorMicrophone.getSoundIntensity(),
    2000
    )
})
```

## step 5
Great, you did it!

Now you can test it out. Does the graph change as the sound changes? What happens if you change the ``||led:up to||`` value for the ``||led.plot bar graph||``? What if you change the small switch on the side of the sensor, does the ``||gatorMicrophone:sound intensity||`` go up or down?


```ghost

basic.forever(function () {
    led.plotBarGraph(
    gatorMicrophone.getSoundIntensity(),
    2000
    )
})
if (0 * 0 == 0 + 0) {

}

```

```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
```
