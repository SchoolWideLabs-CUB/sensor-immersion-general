# Graph Sound Tutorial
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:45581-39253-96150-50774 -->

## Step 1

We are going to learn how to use a micro:bit and gator:microphone to show sound values as a graph on your micro:bit!

```template
basic.forever(function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity())
})
```

## Step 2

Make sure your gator:microphone sensor is still wired correctly to your gator:bit.

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/1oiQ0SdTL-UBnaFOiDmDOU_auGtIwzq84lymv9pf5Y0E/edit?usp=sharing)

To start, remove the ``||basic:show number||`` (Basic) and use the ``||led:plot bar graph||`` (Led) block to display a number as a graph on your micro:bit led screen.

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

This ``||led:plot bar graph||`` (Led) block takes in two oval blocks. The first is the value we want to graph, usually an oval block from a sensor (like our ``||gatorMicrophone:sound intensity||``!).

Change the value being graphed to be the sound with ``||gatorMicrophone:sound intensity||`` (GatorMicrophone).


#### ~ tutorialhint

```blocks
basic.forever(function () {
    led.plotBarGraph(gatorMicrophone.getSoundIntensity(), 0)
})
```   

## step 4

The second oval in the ``||led:plot bar graph||`` (Led) block is the maximum value of our graph.

Most sounds do not go over 2000, so let’s make that value 2000.


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

Now you can test it out. Does the graph change as the sound changes? What happens if you change the second oval for the ``||led.plot bar graph||``? What if you change the small switch on the side of the sensor, does the ``||gatorMicrophone:sound intensity||`` go up or down?

If it does not work, see the hint for a few common issues!

#### ~ tutorialhint
Here are some common issues and their solutions:
1. Check for two red lights next to the 3.3V pin on the gator:bit. If they are off, check the following switch and make sure it is on.
![VOut](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/VOUT_Switch.jpg?raw=true)

2. If the values are very low or very high, check the small switch on the side of the sensor (below). This should be set to medium, directly in the middle.
![Gain Switch](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/Gain_Levels.jpg?raw=true)

3. Otherwise, double check your wiring with the wiring guide [here](https://docs.google.com/document/d/1oiQ0SdTL-UBnaFOiDmDOU_auGtIwzq84lymv9pf5Y0E/edit?usp=sharing).



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
gatorMicrophone=github:sparkfun/pxt-gator-microphone
```
