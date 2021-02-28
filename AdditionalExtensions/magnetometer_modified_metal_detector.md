# magnetometer_modified_metal_detector
# Metal Detector Modified
### @explicitHints true

## Welcome

We are now going to modify your previous metal detector to customize it to your personal interests and make it more advanced 

Submit your answers using the google form under your teacher's name titled "Modified Metal Detector"
 
https://schoolwidelabs.github.io/sensor-immersion-google-forms

```template
input.onButtonPressed(Button.A, function () {
    led.setBrightness(input.magneticForce(Dimension.Strength))
    basic.showIcon(IconNames.Square)
    if (input.magneticForce(Dimension.Strength) > 250) {
        music.playTone(659, music.beat(BeatFraction.Whole))
    }
    basic.showNumber(Math.round(input.magneticForce(Dimension.Strength)))
})
```

## before you begin

Answer question 1 and question 2 on the google form, describing some ideas you have for how to make the metal detector more advanced, more fun, and personalized

## Step 2

Here are some suggestions you can try as you modify the metal detector to make it your own:

1. run in a constant loop ``||basic.forever||`` or other way to start the detector other than ``||input.onButtonPressed||``
2. adding more levels to the ``||logic.if||`` command
3. add in ``||basic.pause||`` or change the ``||music||``
4. use ``||basic.show||`` commands and change what is displayed on the screen
5. add in a ``||loops.loop||`` or a ``||math.math||`` operation

#### ~ tutorialhint
Make sure your ``||logic.if||`` is inside the ``||input.onButtonPressed||`` command


## Step 3

When you are done, **put your answer and a screenshot of your final code in the google form**

Congratulations, you're done!

**Fill out the final question in the google form**

#### ~ tutorialhint
This is what one modified metal detector could look like:
```blocks
basic.forever(function () {
    led.setBrightness(input.magneticForce(Dimension.Strength))
    basic.showIcon(IconNames.Square)
    if (input.magneticForce(Dimension.Strength) > 250) {
        music.playTone(659, music.beat(BeatFraction.Whole))
    } else if (input.magneticForce(Dimension.Strength) > 100) {
        music.playTone(330, music.beat(BeatFraction.Whole))
    } else {
        music.playTone(165, music.beat(BeatFraction.Whole))
    }
})
```
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(262)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        `)
    basic.clearScreen()
    basic.showString("Hello!")
})
basic.pause(100)
while (true) {
	
}
for (let index = 0; index < 0 * 0; index++) {
	
}
music.playMelody("- - - - - - - - ", music.beat(BeatFraction.Whole))
music.rest(music.beat(BeatFraction.Whole))
music.setVolume(0 % 1)
music.ringTone(262)
music.setTempo(120)
music.changeTempoBy(20)
basic.forever(function () {
    led.setBrightness(input.magneticForce(Dimension.Strength))
    basic.showIcon(IconNames.Square)
    if (input.magneticForce(Dimension.Strength) > 250) {
        music.playTone(659, music.beat(BeatFraction.Whole))
    } else if (input.magneticForce(Dimension.Strength) > 100) {
        music.playTone(330, music.beat(BeatFraction.Whole))
    } else {
        music.playTone(165, music.beat(BeatFraction.Whole))
    }
})
```