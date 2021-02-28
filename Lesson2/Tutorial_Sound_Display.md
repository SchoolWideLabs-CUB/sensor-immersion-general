# Sound Sensor Data Display
### @explicitHints true

## Step 1
In this tutorial you are going to learn how to ask questions about the value from
the sound sensor in order to turn on lights and make a sound. The lights are controlled
by Pin 12 on the gator:bit and are already initialized for you. 
The lights are called ``||Variables: strip||``.

The google form for this tutorial is still under development.

```template
input.onButtonPressed(Button.A, function () {
   
})
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
```

## Step 2
When you press ``||input: button A||``, you will ask a question about the data.


#### ~ tutorialhint
What ``||logic: block||`` lets you ask questions about the data?



## Step 3 
``||logic: If||`` the ``||gatorMicrophone: sound intensity||`` is ``||logic: greater than 500||``, turn the ``||Neopixel: lights yellow||``.

## Step 4
``||logic: If||`` the ``||gatorMicrophone: sound intensity||`` is ``||logic: less than or equal to 500||``, turn the ``||Neopixel:lights blue||`` and ``||Music: play a happy song||``.
#### ~ tutorialhint
The value of sound intensity is either more than 500 OR less than or equal to 500. 
The ``||logic: else||`` part of the if-then-else statement can come in handy here.

```ghost
input.onButtonPressed(Button.A, function () {
    if (gatorMicrophone.getSoundIntensity() > 500) {
        strip.showColor(neopixel.colors(NeoPixelColors.Yellow))
    } else {
        strip.showColor(neopixel.colors(NeoPixelColors.Blue))
        music.startMelody(music.builtInMelody(Melodies.Dadadadum), MelodyOptions.Once)
    }
})
let strip: neopixel.Strip = null
strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
```

```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone#v1.0.20
neopixel=github:microsoft/pxt-neopixel#v0.7.3
```










