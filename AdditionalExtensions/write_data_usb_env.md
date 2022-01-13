# Log Environmental Data Using USB
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:89694-88340-30169-53175 -->


## Welcome

We are going to learn how to use a micro:bit to **collect environmental sensor data** and both **store** it and **graph** it on a computer or chromebook.

```template
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {}
```

## Step 2

USB stands for universal serial bus, it is a type of serial port. Today, we will be using "serial" commands that work with your computer's USB port.

Use the ``||loops.everyInterval||`` and ``||serial.Serial write value||`` commands to send temperature values to the computer through the USB port.

#### ~ tutorialhint
```blocks
loops.everyInterval(1000, function () {
    serial.writeValue("x", gatorEnvironment.getMeasurement(measurementType.degreesF))
})
```

## step 3
The micro:bit is reading the temperature value every second and storing it with the title "x". Let's change that title, "x", to something more descriptive. Pick something that makes sense to you.

#### ~ tutorialhint
"temperature", "temp", "temperature fahrenheit", "degrees" are all good examples.

```blocks
loops.everyInterval(1000, function () {
    serial.writeValue("your word goes here", gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
```

## step 4
That's it for programming so it is time to put the program on the micro:bit to test it out. This program needs to have the micro:bit connected via the USB cable to work. If it gets stuck, try hitting the refresh icon to restart the simulator and then click "show console" to see the data.

#### ~ tutorialhint
Let it run for a little and see what the hottest and coldest temperatures you can get are.

## step 5
After it has run for 10+ seconds, click the download button and open the file in Excel or Sheets. This file shows the values of your sensor every second.

![download icon](https://github.com/schoolwidelabs/sensor-immersion/blob/master/static/images/download%20icon.png?raw=true)

```ghost
loops.everyInterval(1000, function () {
    serial.writeValue("temp", gatorEnvironment.getMeasurement(measurementType.degreesF))
})
```

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
