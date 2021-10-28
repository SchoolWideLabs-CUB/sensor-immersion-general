# Log Classroom Data
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:83390-09955-88180-31529 -->

```template
gatorLog.begin()
gatorLog.openFile("fileName.csv")
gatorEnvironment.beginEnvironment()
gatorLog.writeLine("Temperature (F)" + "," + "Humidity" + "," + "VOCs")
loops.everyInterval(500, function () {
    gatorLog.writeLine("replace with temperature" + "," + "replace with humidity" + "," + "replace with VOCs")
})
```

## Step 1
In this tutorial, we will show you how to log data from your classroom to an SD card using the gator:log.

First, you need to wire your environmental sensor and gator:log. Take a look at [this tutorial](https://learn.sparkfun.com/tutorials/sparkfun-gatorlog-hookup-guide/all#hardware-assembly) for instructions and a picture of what it should look like.

## Step 2
Now, let's take a look at the code. There is a lot going on here, so let's go over the new blocks that we see.

First, we have the ``||gatorLog:initialize gator:log||`` block. The gator:log, similar to the gator:environment sensor, needs to be turned on before it can be used. Leave this as is and continue.

## Step 3
Next, we have the ``||gatorLog:open file||`` block. This opens up the file with the name "fileName.csv", where .csv stands for comma separated values. In non-computer terms, this just means that it stores numbers that are each separated by a comma.

Let's change the name of this file to make it describe what we want it to store. Rename the file to (your last name)ClassroomEnvironment.csv and click the arrow to continue.

## Step 4
Last, we have the ``||gatorLog:write line||`` block. This block expects one line consisting of all of our data we want to save, separated by commas. To do this, we need to use the ``||Text:join||`` block.

The ``||Text:join||`` block takes in a bunch of strings and puts them into one long line. By using this, we can directly insert our GatorEnvironment oval blocks into our write line block! This makes it very easy to record data with a micro:bit.

In our first line written to the file, we have the names of the data that we are going to store there. Think of these as the headers, like you would see in an Excel or Google spreadsheet. For the rest of this program, you will store data using the same order (temperature comma humidity comma VOCs).

## Step 5
Now it's time to store some data! If you look at the remaining code, you will see a ``||Loops:every 500 ms||`` event with a ``||gatorLog:write line||`` block inside. This helps us take and store sensor values at regular intervals, so we can use the data later on.

To start recording data, simply replace the first oval with ``||gatorEnvironment:get degreesF||``, the third oval with ``||gatorEnvironment:get humidity||``, and the fifth oval with ``||gatorEnvironment:get TVOCs||``! Leave the commas as they are, this makes sure that the data is recorded properly.

#### ~ tutorialhint

```blocks
loops.everyInterval(500, function () {
    gatorLog.writeLine("" + gatorEnvironment.getMeasurement(measurementType.degreesF) + "," + gatorEnvironment.getMeasurement(measurementType.humidity) + "," + gatorEnvironment.getMeasurement(measurementType.TVOC))
})
```

## Step 6
Let's download this code and start recording data. Make sure that the gator:log has an SD card in it and the wiring is correct. If everything is working properly, you should see a small blue light on the gator:log blink every half of a second (500ms). Record data for a minute or two, and feel free to breathe on the sensor to make the values spike!

## Step 7
Now that we have our data, lets plug the SD card into your computer using the adapter in your gator:bit kit.

Confirm that your file exists and open it in Google Sheets. You should see hundreds of lines of data, starting with our header row "Temerature (F),Humidity,VOCs".

## Step 8
You're finished collecting your data! Now head back to the slides, we're going to do something with this data!

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
gatorLog=github:sparkfun/pxt-gator-log
```
