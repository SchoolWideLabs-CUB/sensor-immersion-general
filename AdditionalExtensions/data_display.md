# Building the Data Display

## Step 1
First we need to ``||gatorEnvironment: initialize||`` the environmental sensor and make 
``||Variables: buckets||`` to hold the sensor values. We call these buckets 
``||Variables: variables||``. This has already been done for you. 
What are the names of the variables?

```template
gatorEnvironment.beginEnvironment()
let Temp = 0
let Humid = 0
let Soil_Moisture = 0
```

## Step 2
We want to show the temperature, humidity, and soil moisture. Let's start by ``||basic: showing||``
the ``||gatorEnvironment: temperature||`` when ``||input: you press button A||``. The value can be a really long decimal, so 
let's ``||math: round it||``. Remember, we always put the value of the sensor in its ``||variables: bucket||``

```blocks
input.onButtonPressed(Button.A, function () {
    Temp = Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF))
    basic.showNumber(Temp)
})
```

## Step 3
We want to show the temperature, humidity, and soil moisture. Let's start by ``||basic: showing||``
the ``||gatorEnvironment: humidity||`` when ``||input: you press button B||``. 
The value can be a really long decimal, so let's ``||math: round it||``. 
Remember, we always put the value of the sensor in its ``||variables: bucket||``

```blocks
input.onButtonPressed(Button.B, function () {
    Humid = Math.round(gatorEnvironment.getMeasurement(measurementType.humidity))
    basic.showNumber(Humid)
})
```

## Step 4
We want to show the temperature, humidity, and soil moisture. Let's start by ``||basic: showing||``
the ``||gatorSoil: soil moisture||`` when ``||input: you press button A and button B at the same time||``. 
The value is a decimal between 0 and 1, so let's ``||math: multiply by it 100||`` 
so we have a percentage moisture and then ``||math: round it||`` so it's easier to read.
let's round it. Remember, we always put the value of the sensor in its ``||variables: bucket||``

```blocks
input.onButtonPressed(Button.AB, function () {
    Soil_Moisture = Math.round(100 * gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
    basic.showNumber(Soil_Moisture)
})
```

## Step 5
Let's download the code and test it out! After you download it and try it out, 
go on to the next step.

## Step 6
Now that we saw the sensor values as numbers, let's use them to create a display. 
We can ask questions about the value of the data using the ``||logic: if then else blocks||``
and the ``||logic: comparison blocks (>, <)||``. Let's ask a question about temperature and have the
micro:bit show different things if it's hot or cold.

```blocks
input.onButtonPressed(Button.A, function () {
    Temp = Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF))
    if (Temp > 75) {
        basic.showString("HOT")
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else {
        basic.showString("OK")
    }
})
```

## Step 7
Now add blocks to your program to ``||logic: ask questions||`` about humidity and soil moisture. 

```blocks
input.onButtonPressed(Button.B, function () {
    Humid = Math.round(gatorEnvironment.getMeasurement(measurementType.humidity))
    if (Humid < 25) {
        basic.showIcon(IconNames.No)
    } else {
        basic.showLeds(`
            # # # # #
            # # # # #
            . # # # .
            . # # # .
            # # # # #
            `)
    }
})

input.onButtonPressed(Button.AB, function () {
    Soil_Moisture = Math.round(100 * gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
    if (Soil_Moisture < 50) {
        basic.showIcon(IconNames.Sad)
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

## Step 8
Let's download the code and test it out! After you download it and try it out, 
go on to the next step.

## Step 9
Let's put everything together in the ``||basic: forever block||``. When we use the 
forever block, it's important to ``||basic: pause||`` between commands so you have time to see what 
happens. The micro:bit does things way too fast for our eyes to see.

```blocks
basic.forever(function () {
    Temp = Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF))
    Humid = Math.round(gatorEnvironment.getMeasurement(measurementType.humidity))
    Soil_Moisture = Math.round(100 * gatorSoil.moisture(AnalogPin.P2, GatorSoilType.Moisture, DigitalPin.P1))
    if (Temp > 75) {
        basic.showString("HOT")
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else {
        basic.showString("OK")
    }
    basic.pause(1000)
    if (Humid < 25) {
        basic.showIcon(IconNames.No)
    } else {
        basic.showLeds(`
            # # # # #
            # # # # #
            . # # # .
            . # # # .
            # # # # #
            `)
    }
    basic.pause(1000)
    if (Soil_Moisture < 50) {
        basic.showIcon(IconNames.Sad)
    } else {
        basic.showIcon(IconNames.Happy)
    }
    basic.pause(1000)
})
```



```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
gatorSoil=github:sparkfun/pxt-gator-soil#v1.0.3
```
