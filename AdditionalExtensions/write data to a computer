# sound intensity logging from the USB port
### @explicitHints true
 
## Welcome

We are going to learn how to use a micro:bit to **collect sound sensor data** and both **store** it and **graph** it on a computer or chromebook.
 
```template
loops.everyInterval(1000, function () {}
```
 
## Step 2
 
USB stands for universal serial bus, it is a type of serial port. Today, we will be using "serial" commands that work with your computer's USB port. 

Use the ``||loops.everyInterval||`` and ``||serial.serial write Value||`` commands to send sound sensor values to the computer through the USB port 
 
#### ~ tutorialhint
```blocks
loops.everyInterval(1000, function () {
    serial.writeValue("x", gatorMicrophone.getSoundIntensity()))
})
```
 
## step 3
The micro:bit is reading the sound value every second and storing it with the title "x". Let's change that title, "x", to something more descriptive. Pick something that makes sense to you

#### ~ tutorialhint
"sound" "sound value" "sound intensity" "noise" "loudness" are all good examples 

```blocks
loops.everyInterval(1000, function () {
    serial.writeValue("your word goes here", gatorMicrophone.getSoundIntensity()))
})
```
 
## step 4
That's it for programming so it is time to put the program on the micro:bit to test it out. This program needs to have the micro:bit connected via the USB cable to work. If it gets stuck, try hitting the refresh icon to restart the simulator and then click "show console" to see the data
 
#### ~ tutorialhint
Let it run for a little and see what the loudest and quietist sounds you can get are.

## step 5
After it has run for 10+ seconds, click the download button and open the file in Excel or Sheets. This file shows the values of your sensor every second. 

![download icon](https://github.com/schoolwidelabs/sensor-immersion/blob/master/static/images/download%20icon.png?raw=true)

```ghost
loops.everyInterval(1000, function () {
    serial.writeValue("sound value", gatorMicrophone.getSoundIntensity())
})
```
  
```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
```

