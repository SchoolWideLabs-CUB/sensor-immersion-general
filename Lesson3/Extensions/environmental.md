# Pressure and Humidity Gauge
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:38751-84751-08092-93200 -->

```template
input.onButtonPressed(Button.A, function () {  basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.pressure)))
})
gatorEnvironment.beginEnvironment()
```

## Step 1

We are going to build off of a simple pressure gauge and instead use variables to have it alternate between showing the pressure and showing the humidity.

## Step 2

First, we are going to make a "dummy variable" called "humidity" which tells the program if it is reading humidity (humidity=1) or not (humidity=0). Dummy variables have a value of either 1 or 0 and can act as a switch in a program to turn something on or off, changing between one of two states.

In ``||basic:on start||`` (Basic), create a ``||variables:variable||`` (Variables) with the ``||variables:set||`` (Variables) command and call it "humidity". Then set it to 1.

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/1bxYGD53_5G7AXUVdqf0oQRN7OQ0Bnc9e/view?usp=sharing)

#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.pressure)))
})
gatorEnvironment.beginEnvironment()
let humidity = 1
```

## Step 3
Now you are going to modify what happens when ``||input:button A is pressed||`` (Input). Instead of having it show you the humidity, use Logic to have it show you the humidity ``||logic:if||`` the variable "humidity" = 1 and the pressure if the variable "humidity" = 0.

#### ~ tutorialhint
The ``||logic:if else||`` (Logic) command works well for this but you can organize the Logic however you choose, feel free to experiment!

## Step 4
Currently the program has no way to change between the two values for "humidity". After it shows the humidity, have it ``||variables:set||`` (Variables) "humidity" to 0. After it shows the pressure, have it ``||variables:set||`` (Variables) the "humidity" to 1.

## Step 5
One last step, how do you know your program is working and showing humidity or pressure? Add a ``||basic:show string||`` (Basic) to show the letter 'H' right before it shows humidity. Repeat this with the letter 'P' right before it shows pressure.

#### ~ tutorialhint
If the letter flashes too quickly, add a ``||basic:pause||`` (Basic) command between the two commands so you can see the letter.

## Step 6
Congratulations, you are done! If you need to see an example of a working program, check the hint.

#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    if (humidity == 1) {
        basic.showString("H")
        basic.pause(1000)
        basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
        humidity = 0
    } else if (humidity == 0) {
        basic.showString("P")
        basic.pause(1000)
        basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.pressure)))
        humidity = 1
    }
})
let humidity = 0
gatorEnvironment.beginEnvironment()
humidity = 1
```

```ghost
input.onButtonPressed(Button.A, function () {
    if (Humidity == 1) {
        basic.showString("H")
        basic.pause(1000)
        basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
        Humidity = 0
    } else if (Humidity == 0) {
        basic.showString("P")
        basic.pause(1000)
        basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.pressure)))
        Humidity = 1
    }
})
let Humidity = 0
gatorEnvironment.beginEnvironment()
Humidity = 1
```

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
