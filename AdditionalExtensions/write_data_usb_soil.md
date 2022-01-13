# Log Soil Moisture Data Using USB
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:86475-72787-80255-09387 -->


## Welcome

We are going to learn how to use a micro:bit to **collect soil moisture data** and both **store** it and **graph** it on a computer or chromebook.

```template
loops.everyInterval(1000, function () {}
```

## Step 2

USB stands for universal serial bus, it is a type of serial port. Today, we will be using "serial" commands that work with your computer's USB port.

Use the ``||loops.everyInterval||`` and ``||serial.Serial write value||`` commands to send a soil moisture sensor value to the computer through the USB port.

#### ~ tutorialhint
```blocks
loops.everyInterval(1000, function () {
    serial.writeValue("x", gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```

## step 3
The micro:bit is reading the soil moisture value every second and storing it with the title "x". Let's change that title, "x", to something more descriptive. Pick something that makes sense to you.

#### ~ tutorialhint
"soil", "soil moisture", and "moisture" are all good examples.

```blocks
loops.everyInterval(1000, function () {
    serial.writeValue("your word goes here", gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```

## step 4
That's it for programming! It is time to put the program on the micro:bit to test it out. This program needs to have the micro:bit connected via the USB cable to work.

If it gets stuck, try hitting the refresh icon to restart the simulator and then click "**Show console** Device" to see the data.

#### ~ tutorialhint
Let it run for a little and see what the different moisture values you can get are.

## step 5
After it has run for 10+ seconds, click the download button in the top right corner of the "**Show console** Device" window and open the file in Excel or Google Sheets. This file shows the values of your sensor every second.

![download icon](https://github.com/schoolwidelabs/sensor-immersion/blob/master/static/images/download%20icon.png?raw=true)

```ghost
loops.everyInterval(1000, function () {
    serial.writeValue("x", gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
})
```

```package
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
