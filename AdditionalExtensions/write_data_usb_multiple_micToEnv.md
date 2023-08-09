# Storing data from multiple inputs
### @explicitHints true
 
## Welcome

```template
loops.everyInterval(1000, function () {
    serial.writeValue("your word goes here", gatorMicrophone.getSoundIntensity())
})
```

Now that we know how to store data from the sound sensor on your computer, it is time to modify your program to have different input values, instead of Sound, we wil use Temperature, Humidity and Total Volitile Organic Compounds (TVOC).
 
Before you start, make sure to add the ``||gatorEnvironment: initialize||`` command in an ``||basic: on start||`` event for the GatorEnvironment sensors.

#### ~ tutorialhint
```blocks
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("your word goes here", gatorMicrophone.getSoundIntensity())
})
```
 
## Step 2

Now to change what you are measuring to temperature you need to change two things.

1. Rename your varialbe, we called it "temp" in the hint
2. Change the red inupt value from ``||gatorMicrophone:sound intensity||`` to ``||gatorEnvironment:get degreesF||``

#### ~ tutorialhint
```blocks
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", gatorEnvironment.measurement(MeasurementType.degreesF))
})
```
 
## step 3
Great! now you want to round your values for temperature using the ``||math:round||`` block

#### ~ tutorialhint

```blocks
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", Math.round(gatorEnvironment.measurement(MeasurementType.degreesF)))
})
```
 
## step 4
right click (click with two fingers if on chromebook) on the ``||serial:serial write value||`` block and select duplicate

Make two copies and put them in your ``||loops:every||`` event loop

#### ~ tutorialhint

```blocks
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", Math.round(gatorEnvironment.measurement(MeasurementType.degreesF)))
    serial.writeValue("temp", Math.round(gatorEnvironment.measurement(MeasurementType.degreesF)))
    serial.writeValue("temp", Math.round(gatorEnvironment.measurement(MeasurementType.degreesF)))
})
```

##step 5
now you need to change two things inside your second and third ``||serial:serial||`` blocks 

1. Change the value labels to "humidity" and "TVOC"
2. Change the input value to ``||gatorEnvironment:get humidity values||`` and ``||gatorEnvironment:get TVOC value||``

#### ~ tutorialhint

```blocks
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", Math.round(gatorEnvironment.measurement(MeasurementType.degreesF)))
    serial.writeValue("humidity", Math.round(gatorEnvironment.measurement(MeasurementType.humidity)))
    serial.writeValue("TVOC", Math.round(gatorEnvironment.measurement(MeasurementType.TVOC)))
})
```


## step 6
You are done programming! Now connect your microbit to your computer by clicking "connect device" in the three dots next to download. 

Once connected, click download to move your program to the microbit.

The old option to download it to the computer and then drag it onto the micro:bit icon will not work for this program!

![connect device](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/static/images/connect%20device.png?raw=true)

#### ~ tutorialhint
this is what the purple download button will look like once the micro:bit is connected
![connected download](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/static/images/connected%20download.png?raw=true)

##step 7
Now that you are connected, click on "Show console Device" while the micro:bit is still plugged into your computer. Walk around and collect data in real time!

![show console device](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/static/images/show%20console%20device.png?raw=true)

### ~ tutorialhint
If you only see "Show console Simulator" then your micro:bit is not connected and synched to the computer, go back to step 6

![show console simulator only](https://github.com/schoolwidelabs/sensor-immersion-general/blob/master/static/images/show%20console%20simulator%20only.png?raw=true)


##step 8
When you are done you can download the data using the download icon
![download icon](https://github.com/schoolwidelabs/sensor-immersion/blob/master/static/images/download%20icon.png?raw=true)


```ghost
gatorEnvironment.beginEnvironment()
loops.everyInterval(1000, function () {
    serial.writeValue("temp", Math.round(gatorEnvironment.measurement(MeasurementType.degreesF)))
    serial.writeValue("humidity", Math.round(gatorEnvironment.measurement(MeasurementType.humidity)))
    serial.writeValue("TVOC", Math.round(gatorEnvironment.measurement(MeasurementType.TVOC)))
})
```
  
```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone
gatorEnvironment=github:sparkfun/pxt-gator-environment
```
