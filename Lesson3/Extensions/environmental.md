# pressure and humidity gauge
### @explicitHints true
 
```template
input.onButtonPressed(Button.A, function () {  basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
})
gatorEnvironment.beginEnvironment()
```
 
## Step 1
 
We are going to build off of a simple pressure gauge and instead use variables to have it alternate between showing the pressure and showing the humidity. 
 
Submit your final code to your teacher on schoology (or wherever your teacher asks)
 
## Step 2
 
First, we are going to make a "dummy variable" called "humidity" which tells the program if it is reading humidity (humidity=1) or not (humidity=0). Dummy variables have a value of either 1 or 0 and can act as a switch in a program to turn something on or off, changing between one of two states. 

Create a ``||variables:variable||`` with the ``||variables:set||`` command and call it "humidity". Then set it to 1.
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.pressure)))
})
gatorEnvironment.beginEnvironment()
let humidity = 1
```

## Step 3
Now you are going to modify what happens when you press button A. Insead of having it show you the humidity, have it show you the humidity if the variable "humidity" =1 and the pressure if the variable "humidity" =0.

#### ~ tutorialhint
The ``||logic:else if||`` command works well for this but is not required. You can set it up with conditions for both ``||logic:if||`` humidity=1 and ``||logic:else if||`` humidity=0 or just use an ``||logic:if||`` command for what happens for one value of humidity and then specify what happens if that is not true. 

## Step 4
Currently the program has now way to change between the two values for "humidity". After it shows the humidity, have it ``||variables:set||`` "humidity" to 0. After it shows the pressure, have it ``||variables:set||`` the "humidity" to 1. 

## Step 5
One last step, how do you know your program is working and showing humidity or pressure? Add a ``||basic:show string||`` to show the letter h right before it shows humidity and then one to show the letter p right before it shows pressure.

## Step 6
Congratulations, you are done! If you need to see an example of a working program, check the hint.

#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    if (humidity == 1) {
        basic.showString("h")
        basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
        humidity = 0
    } else if (humidity == 0) {
        basic.showString("p")
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
        basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
        Humidity = 0
    } else if (Humidity == 0) {
        basic.showString("P")
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
