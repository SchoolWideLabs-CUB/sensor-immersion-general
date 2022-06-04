# Measure Four Values
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:99089-68980-21536-58052 -->

## Step 1
We are going to use the gator:environment, gator:soil, and an onboard sensor to measure and display 4 values!

```template
input.onButtonPressed(Button.A, function () {

})
input.onButtonPressed(Button.AB, function () {

})
input.onButtonPressed(Button.B, function () {

})
input.onGesture(Gesture.Shake, function () {

})
gatorEnvironment.beginEnvironment()
basic.showIcon(IconNames.Yes)
```

## Step 2
First, make sure the gator:environment AND gator:soil sensors are wired to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/1ImyySsggWb83fH_bqrgn5fYdSNAkpBV_N31UL_JWuII/edit?usp=sharing)

## Step 3
Next, we are going to use the four provided ``||Input:Input||`` events to display our four sensor values. We will do each one at a time, feel free to test your code either at each step or all at once at the end!

Press the arrow to continue to the next step.

## Step 4
First, let us display the current temperature in ``||input:on button A pressed||``.

To do this, simply use the ``||basic:show number||`` (Basic) and ``||gatorEnvironment:get degreesF||`` (GatorEnvironment) blocks inside of the Button A input event.

#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.degreesF))
})
```

## Step 5
Next, lets display the humidity level in the ``||input:on button A+B pressed||`` event.

This follows the same process; use the ``||basic:show number||`` (Basic) and ``||gatorEnvironment:get humidity||`` (GatorEnvironment) blocks inside the buttons A+B pressed event.

#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.AB, function () {
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.humidity))
})
```

## Step 6
Next, lets display the soil moisture level in the ``||input:on button B pressed||`` event.

This follows a similar process; use the ``||basic:show number||`` (Basic) and ``||gatorSoil:get moisture||`` (GatorSoil) blocks inside the button B pressed event.


#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.B, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```

## Step 7
Lastly, let us show the light level in the ``||input:on shake||`` event! The light sensor is one of the sensors on the micro:bit board, you will find this value in the ``||input:Input||`` drawer!

Follow the same process to show the number in the on shake event.

#### ~ tutorialhint
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(input.lightLevel())
})
```

## Step 8
You're done! Next, download your code to your micro:bit and test it out!

If it's not working, check the hint below to see some common issues.

#### ~ tutorialhint
Here are some common issues and their solutions:
1. Check for two red lights next to the 3.3V pin on the gator:bit. If they are off, check the following switch and make sure it is on.
![VOut](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/VOUT_Switch.jpg?raw=true)

2. Double check that your P# values and your wiring matches up! The first value in the block (P2) should match the green wire, the second value (P1) should match the red wire. Also, do not use P0 for the power pin (red wire), it will not work.
![Soil Block](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/gatorsoil_get_block.PNG?raw=true)

3. Otherwise, double check your wiring with the wiring guide [here](https://docs.google.com/document/d/1ImyySsggWb83fH_bqrgn5fYdSNAkpBV_N31UL_JWuII/edit?usp=sharing).



```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.degreesF))
})
input.onButtonPressed(Button.AB, function () {
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.humidity))
})
input.onButtonPressed(Button.B, function () {
    basic.showNumber(gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(input.lightLevel())
})
gatorEnvironment.beginEnvironment()
basic.showIcon(IconNames.Yes)
```

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
