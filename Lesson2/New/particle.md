# show particle tutorial
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gatorMicrophone to display particle values using red light. 
First we have to ``||gatorParticle: initialize||`` the particle sensor when we ``||basic: turn on||`` the micro:bit.
 
```template
input.onButtonPressed(Button.A, function () {
    
})
```

#### ~ tutorialhint 
```blocks
gatorParticle.begin()
```
 
## Step 2
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
## Step 3
 
To start, use the ``||basic:show number||`` command to display any number when button a is pressed
 
#### ~ tutorialhint
Try clicking on the 'Basic' drawer to find the block you need!
 
```blocks
input.onButtonPressed(Button.A, function () {
	basic.showNumber(0)
})
```
 
## Step 4
 
Now change the value of ``||basic:showNumber||`` to be the red value with ``||gatorPartice:get red value||`` 
 
 
#### ~ tutorialhint
 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorParticle.color(LEDToRead.Red))
})
```
 
## step 5 
 
In the ``||math.math||`` menu you will find the ``||math.round||`` command to round to the nearest whole number
 
Use this command to change the displayed value to be the red value rounded to the nearest whole number
 
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorParticle.color(LEDToRead.Red)))
})
```
 
## step 6
Great! You did it. Now you can test it out. How could you modify it to take 
your ``||gatorParticle: heart rate||``? 

### ~ tutorialhint
Look for the particle block that says bpm for beats per minute.
```blocks
input.onButtonPressed(Button.A, function () {
	basic.showNumber(gatorParticle.heartbeat(HeartbeatType.BPM))
})
```
 
 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorMicrophone.getSoundIntensity()))
})
if (0 * 0 == 0 + 0) {
    
}
 
```
 
```package
gatorParticle=github:sparkfun/pxt-gator-particle#v1.1.3
```