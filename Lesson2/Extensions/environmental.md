# Show Temperature CO2 and Humidity Data with the Environmental Sensor
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:50699-08414-81210-87043 -->

## Step 1

We are going to learn how to program a micro:bit and gator:bit environmental sensor to display temperature, CO2, and humidity values!

```template
gatorEnvironment.beginEnvironment()
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
```

## Step 2

First, make sure your gator:environment sensor is still wired to your gator:bit!

If you need help with wiring, take a look at [this guide.](https://drive.google.com/file/d/1bxYGD53_5G7AXUVdqf0oQRN7OQ0Bnc9e/view?usp=sharing)

Provided below is the code you completed in the Show Temperature tutorial in Lesson 2.

## Step 3

Now before we are going to add the display for the other sensors, we should label this one so we know what reading we are getting.

Above the ``||basic:show number||`` (Basic) block, add a ``||basic:show string||`` (Basic) block and have it show 'Temp' so you know that you are seeing the temperature.

#### ~ tutorialhint

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("Temp")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})

```

## Step 4
Great!

Now, duplicate your show temperature blocks with different ``||input:Input||`` (Input) events to show other environmental data like humidity and CO2.

Make sure you use ``||basic:show string||`` (Basic) to label them so you know what readings are being displayed.

#### ~ tutorialhint
By right-clicking on the Input event, you can duplicate the entire event with all its blocks!

It could look like this, there are many correct answers:

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showString("Temp")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
input.onButtonPressed(Button.B, function () {
    basic.showString("Humidity")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
})
input.onGesture(Gesture.Shake, function () {
    basic.showString("CO2")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.eCO2)))
})
gatorEnvironment.beginEnvironment()

```

## Step 5

Great job! You can now see multiple different things from one program!

```ghost
input.onButtonPressed(Button.A, function () {
    basic.showString("Temp")
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
input.onButtonPressed(Button.B, function () {
    basic.showString("Humidity")
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.humidity))
})
input.onGesture(Gesture.Shake, function () {
    basic.showString("CO2")
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.eCO2))
})
gatorEnvironment.beginEnvironment()
if (0 * 0 == 0 + 0) {}
```


```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
