# magnetometer_display_magnetic_field_radio_two_microbits_and_simulator
# display magnetic field radio, two micro:bits and simulator
### @explicitHints true

## Welcome

We are going to learn how to use two micro:bits to collect data on the magnetic force that you can see on your computer screen. One will collect data and send it to the other that is plugged into the computer and creating the graph.

Submit your answers using the google form with your teacher's name that ends with "display magnetic field radio, two micro:bits and simulator"

https://schoolwidelabs.github.io/sensor-immersion-google-forms/ 

```template
input.onButtonPressed(Button.A, function () {
	})
```

## before you begin

Answer question 1 on the google form, write your thoughts on why would we want to display and collect the data we from a sensor on the computer instead of just showing the numbers on the micro:bit?

## Step 2
We are going to use the same program for the transmitter and the receiver. Both need to be communicating on the same radio channel to talk to one another.

Use the ``||radio:setGroup||`` command and tell the program to set to a channel of your choice when the program starts

#### ~ tutorialhint
```blocks
radio.setGroup(42)
```

## Step 3
Now, when you tap a button on it, the transmitting micro:bit (the one detecting the magnet) needs to send a signal showing the strength of the magnetic field. 

Use the ``||input.onButtonPressed||`` and ``||radio.radio||`` commands to send magneticForce strength

#### ~ tutorialhint
rounding is optional
```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendNumber(input.magneticForce(Dimension.Strength))
})
```

## step 4 
instead of having it just send one time when you press button A, have it ``||loops.repeat||`` for 600 times and ``||basic.pause||`` for 100ms after sending each writeValue

100ms is 1/10th of a second. If we do that 600 times it will last for 60 seconds

This means the transmitter will tell the receiver 600 values of the magneticForce over 60 seconds.

#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 4; index++) {
        radio.sendNumber(input.magneticForce(Dimension.Strength))
        basic.pause(100)
    }
})
```

## step 5
now we need to program what happens when the receiver is told the radio signal from the transmitter

Start with ``||radio.onReceivedNumber||`` and have it ``||serial.writeValue||`` equal to the receivedNumber

### ~ tutorialhint
```blocks
radio.onReceivedNumber(function (receivedNumber) {
    serial.writeValue("magnetic_force", receivedNumber)
})
```

## step 6
Great! You did it. Now you can test it out. Don't forget to hit the refresh icon to restart the simulator and then click "show console" to see the data

**Don't forget to fill out the final questions on the goolge form.**

```ghost
radio.onReceivedNumber(function (receivedNumber) {
    serial.writeValue("magnetic_force", receivedNumber)
})
input.onButtonPressed(Button.A, function () {
    for (let index = 0; index < 600; index++) {
        radio.sendNumber(Math.round(input.magneticForce(Dimension.Strength)))
        basic.pause(100)
    }
})
radio.setGroup(2)
```
