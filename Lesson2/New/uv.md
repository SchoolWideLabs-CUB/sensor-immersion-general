# show uv tutorial
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gatorUV sensor to display UV reading. 
First we have to ``||gatorUV: initialize||`` the uv sensor when we ``||basic: turn on||`` the micro:bit.
 
```template
input.onButtonPressed(Button.A, function () {
    
})
```

#### ~ tutorialhint 
```blocks
gatorUV.begin()
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
 
Now change the value of ``||basic:showNumber||`` to be the uv value with ``||gatorUV:get UVA value||`` 
 
 
#### ~ tutorialhint
 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorUV.UV())
})
```
 
## step 5 
 
In the ``||math.math||`` menu you will find the ``||math.round||`` command to round to the nearest whole number
 
Use this command to change the displayed value to be the uv value rounded to the nearest whole number
 
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorUV.UV()))
})
```
 
## step 6
Great! You did it. Now you can test it out. How can you use the value to figure out the UV index?

### ~ tutorialhint
Take a look at [this webpage.](https://learn.sparkfun.com/tutorials/sparkfun-gatoruv-hookup-guide/makecode-examples)
 
 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorUV.UV()))
})
if (0 * 0 == 0 + 0) {
    
}
 
```
 
```package
gatorUV=github:sparkfun/pxt-gator-UV#v0.1.2
```