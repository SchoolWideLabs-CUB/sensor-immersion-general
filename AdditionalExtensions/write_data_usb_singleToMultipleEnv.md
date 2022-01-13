# Storing Multiple Env Data
### @explicitHints true

<!-- Tutorial Link: https://makecode.microbit.org/#tutorial:69898-99206-78709-93017 -->

## Welcome

```template
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", gatorEnvironment.getMeasurement(measurementType.degreesF))
})
```

Now that we know how to store temperature data on your computer, it is time to modify your program to have multiple input values.

In this tutorial, we will save Temperature, Humidity and Total Volitile Organic Compounds (TVOC) data. Click Next to get started!

## Step 2
First, let us round the temperature value inside of our ``||serial:serial write||`` block using the ``||math:round||`` block.

#### ~ tutorialhint

```blocks
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
```

## Step 3
Next, let us start expanding this to include other environmental values!

Right click (click with two fingers if on a chromebook) on the ``||serial:serial write value||`` block and select duplicate.

Make two copies and put them in your ``||loops:every||`` event loop.

#### ~ tutorialhint
```blocks
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
    serial.writeValue("temp", Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
    serial.writeValue("temp", Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
```

## Step 4
Now, let us change a couple of things in the second and third ``||serial:serial||`` blocks:

1. Change the value labels to "humidity" (second ``||serial:serial||`` block) and "TVOC" (third ``||serial:serial||`` block)
2. Change the input value to ``||gatorEnvironment:get humidity value||`` (second) and ``||gatorEnvironment:get TVOC value||`` (third)

#### ~ tutorialhint

```blocks
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
    serial.writeValue("humidity", Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
    serial.writeValue("TVOC", Math.round(gatorEnvironment.getMeasurement(measurementType.TVOC)))
})
```

## step 5
You are done programming! Now connect your micro:bit to your computer by clicking "Connect Device" in the three dots next to download.

Once connected, click download to move your program to the micro:bit.

The old option to download it to the computer and then drag it onto the micro:bit icon will not work for this program!

![connect device](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/static/images/connect%20device.png?raw=true)

#### ~ tutorialhint
This is what the purple download button will look like once the micro:bit is connected
![connected download](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/static/images/connected%20download.png?raw=true)

## Step 6
Now that you are connected, click on "**Show console** Device" while the micro:bit is still plugged into your computer. Walk around and collect data in real time!

![show console device](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/static/images/show%20console%20device.png?raw=true)

### ~ tutorialhint
If you only see "**Show console** Simulator" then your micro:bit is not connected and synched to the computer, go back to step 5.

![show console simulator only](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/static/images/show%20console%20simulator%20only.png?raw=true)

## Step 7
When you are done, you can download the data using the download icon in the top right corner.
![download icon](https://github.com/schoolwidelabs/sensor-immersion/blob/master/static/images/download%20icon.png?raw=true)


```ghost
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
    serial.writeValue("humidity", Math.round(gatorEnvironment.getMeasurement(measurementType.humidity)))
    serial.writeValue("TVOC", Math.round(gatorEnvironment.getMeasurement(measurementType.TVOC)))
})
```

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
