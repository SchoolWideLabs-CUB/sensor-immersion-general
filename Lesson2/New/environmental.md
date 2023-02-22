# Collecting Temperature Data with the Environmental Sensor
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:68006-23108-64231-19535 -->

## Step 1

We are going to learn how to use a micro:bit and gator:bit environmental sensor to show the temperature in the room.

```template
basic.showIcon(IconNames.Yes)
input.onButtonPressed(Button.A, function () {

})
```

## Step 2

First, you need to wire the gator:environment sensor to your gator:bit!

If you need help with wiring, take a look at [this guide](https://docs.google.com/document/d/1Wy_TLucsBvOR2eAHqqLUJwxPPhVsipK1Qq8MdPxL1X4/edit?usp=sharing).

## Step 3

To start, use the ``||gatorEnvironment: initialize sensors||`` (GatorEnvironment) block to turn the sensors on.

Start the sensor when the micro:bit powers on, inside the ``||basic:on start||`` (Basic) event.

## Step 4

Use the ``||basic:show number||`` (Basic) block to show a value on the micro:bit's led screen in ``||input:button A is pressed||`` (Input). It can be any number you want!

## Step 5

Next, let's replace your number with the temperature from the sensor. Drag the ``||gatorEnvironment:get value||`` (GatorEnvironment) block to where your number is and replace it inside the ``||basic:show number||`` (Basic) block.

Make sure it snaps into the right place!

The value your environment sensor wants to display will be the temperature in degrees Celsius (``||gatorEnvironment:degreesC||``). Using the dropdown, what else can you display using the environmental sensor?

#### ~ tutorialhint
``||gatorEnvironment:degreesC||``: Temperature in Celsius.

``||gatorEnvironment:degreesF||``: Temperature in Fahrenheit.

``||gatorEnvironment:humidity||``: The relative humidity, measured as a percentage (0 - 100).

``||gatorEnvironment:pressure||``: Barometric pressure, measured in Pascals. This changes at different altitudes, with sea level showing ~102,000 Pascals.

``||gatorEnvironment:eCO2||``: The equivalent CO2 levels in the room, measured in parts per million. This can be raised by breathing on the sensor!

``||gatorEnvironment:TVOC||``: The total volatile organic compounds in the room, measured in parts per billion. This can be raised by breathing on the sensor!


## Step 6

That number looks ugly, let's clean it up. To round to the nearest whole number, we can use the ``||Math: round||`` (Math) block. The ``||gatorEnvironment:get value||`` (GatorEnvironment) oval will go into this new ``||Math.round||`` (Math) oval, which will go into the ``||basic:show number||`` (Basic) block.

This will show the temperature as a whole number, much better!

#### ~ tutorialhint

Rounding makes the value easier to read on the display.

Instead of seeing 72.9999999999, you just see 73.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorEnvironment.measurement(MeasurementType.degreesF))
})

```

## Step 7
Great, you did it!

Now you can test it out. How could you use the ``||Math:Math||`` blocks to change the display to two times the temperature? Would you round before or after you double the temperature?

If it does not work, see the hint for a few common issues!

#### ~ tutorialhint
Here are some common issues and their solutions:
1. Check for two red lights next to the 3.3V pin on the gator:bit. If they are off, check the following switch and make sure it is on.
![VOut](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/VOUT_Switch.jpg?raw=true)

2. If nothing is happening, double check to see if you initialized the sensor using the ``||gatorEnvironment:initialize gator:environment sensors||`` block in the ``||basic:on start||`` event!

3. Otherwise, double check your wiring with the wiring guide [here](https://docs.google.com/document/d/1Wy_TLucsBvOR2eAHqqLUJwxPPhVsipK1Qq8MdPxL1X4/edit?usp=sharing).


```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round((gatorEnvironment.measurement(MeasurementType.degreesF)))
})
gatorEnvironment.beginEnvironment()
```

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
