# Pressure and Humidity Gauge
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:66594-32206-49311-97668 -->

```template
input.onButtonPressed(Button.A, function () {  basic.showNumber(Math.round(gatorEnvironment.measurement(MeasurementType.humidity)))
})
gatorEnvironment.beginEnvironment()
```

## Step 1

We are going to build off of a simple pressure gauge (provided below!) and instead use variables to have it alternate between showing the pressure and showing the humidity.

## Step 2

First, we need to make sure that the gator:environment sensor is still correctly wired to the gator:bit!

If you need help with wiring, take a look at [this guide.](https://docs.google.com/document/d/1Wy_TLucsBvOR2eAHqqLUJwxPPhVsipK1Qq8MdPxL1X4/edit?usp=sharing)

## Step 3

First, we are going to make a "dummy variable" called "switch" which tells the program if it is reading humidity (switch=1) or pressure (switch=0). Dummy variables have a value of either 1 or 0 and can act as a switch in a program to turn something on or off, changing between two states.

Create this variable by selecting ``||Variables:Make a Variable...||`` (Variables) and naming it 'switch'.

In the ``||basic:on start||`` (Basic) event, use the ``||Variables:set switch||`` (Variables, after you make the variable 'switch') block to set the switch to 1.

#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.measurement(MeasurementType.pressure)))
})
gatorEnvironment.beginEnvironment()
let humidity = 1
```

## Step 4
Now you are going to modify what happens when ``||input:button A is pressed||`` (Input). Instead of having it show you the humidity, use an ``||Logic:if else statement||`` (Logic) to have it show you the humidity ``||logic:if||`` the variable 'switch' = 1, otherwise (``||Logic:else||``) show the pressure.

Use the skills you learned last lesson to create the ``||Logic:if else statement||``!

#### ~ tutorialhint
The ``||logic:if else||`` (Logic) command works well for this but you can organize the Logic however you choose, feel free to experiment!

## Step 5
Currently, the program has no way to change between the two values for 'switch'. After it shows the humidity, use the ``||variables:set||`` (Variables) block to set 'switch' to 0. After it shows the pressure, have it ``||variables:set||`` (Variables) 'switch' to 1.

## Step 6
One last step, how do you know your program is working and showing humidity or pressure? Add a ``||basic:show string||`` (Basic) block to show the letter 'H' right before it shows humidity. Repeat this with the letter 'P' right before it shows pressure.

#### ~ tutorialhint
If the letter flashes too quickly, add a ``||basic:pause||`` (Basic) block between the two blocks so you can see the letter.

## Step 7
Congratulations, you are done!

If you are having other issues, see the bottom of the hint for common issues!

#### ~ tutorialhint
Here is one example of a working program:
```blocks
input.onButtonPressed(Button.A, function () {
    if (humidity == 1) {
        basic.showString("H")
        basic.pause(1000)
        basic.showNumber(Math.round(gatorEnvironment.measurement(MeasurementType.humidity)))
        humidity = 0
    } else if (humidity == 0) {
        basic.showString("P")
        basic.pause(1000)
        basic.showNumber(Math.round(gatorEnvironment.measurement(MeasurementType.pressure)))
        humidity = 1
    }
})
let humidity = 0
gatorEnvironment.beginEnvironment()
humidity = 1
```

Here are some common issues and their solutions:
1. Check for two red lights next to the 3.3V pin on the gator:bit. If they are off, check the following switch and make sure it is on.
![VOut](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/VOUT_Switch.jpg?raw=true)

2. If the speaker is not making any noise, check this switch and make sure it is on:
![Speaker](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/images/SPEAKER_Switch.jpg?raw=true)

3. Otherwise, double check your wiring with the wiring guide [here](https://docs.google.com/document/d/1Wy_TLucsBvOR2eAHqqLUJwxPPhVsipK1Qq8MdPxL1X4/edit?usp=sharing).


```ghost
input.onButtonPressed(Button.A, function () {
    if (Humidity == 1) {
        basic.showString("H")
        basic.pause(1000)
        basic.showNumber(Math.round(gatorEnvironment.measurement(MeasurementType.humidity)))
        Humidity = 0
    } else if (Humidity == 0) {
        basic.showString("P")
        basic.pause(1000)
        basic.showNumber(Math.round(gatorEnvironment.measurement(MeasurementType.pressure)))
        Humidity = 1
    }
})
let Humidity = 0
gatorEnvironment.beginEnvironment()
Humidity = 1
```

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment
```
