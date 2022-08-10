# Log Classroom Data
### @explicitHints true

<!-- Tutorial: https://makecode.microbit.org/#tutorial:54405-06893-73484-37653 -->


## Step 1
In this tutorial, you will log temperature, humidity, and air quality data from your classroom to an SD card using the gator:log.

First, you need to wire your environmental sensor and gator:log. Take a look at [this wiring tutorial](https://learn.sparkfun.com/tutorials/sparkfun-gatorlog-hookup-guide/all#hardware-assembly) for instructions and a picture of what it should look like.

## Step 2
Now, let's begin programming! First, as we will be using the environmental sensor, place the ``||GatorEnvironment:initialize gator:Environment sensors||`` block from the ``||GatorEnvironment:GatorEnvironment||`` drawer in ``||Basic:on start||``.

Next, take a look into your ``||GatorLog:GatorLog||`` drawer on the left side of the coding window.

The first thing you should notice is the ``||GatorLog:initialize gator:log||`` block. This sensor, similar to the environmental sensor, needs to be turned on before you can use it. Place this ``||GatorLog:initialize||`` block into your ``||Basic:on start||`` event under your ``||gatorEnvironment:initialize gator:environment sensors||`` block.

#### ~ tutorialhint
```blocks
gatorLog.begin()
gatorEnvironment.beginEnvironment()
```

## Step 3
Next, we need to choose where to store all of this data. To do this, we need to open a new .csv file. CSVs, or comma separated values, are simply files that have data in them separated by commas.

To open a .csv on a computer, you open it with Excel or Google Sheets. As this is what we will be doing later in the tutorial, think of these in terms of an Excel / Google spreadsheet.

Every row, instead of being cells, are simply values separated by commas. To go to the next row, you go to a new line. Click next to continue.

## Step 4
Let's create our .csv! In the GatorLog drawer, place the block ``||gatorLog:open file named " "||`` below your current code in ``||basic:on start||``.

Let's give this file a simple name to tell us what it is. As this is the first time we are saving data to a file, name it "data.csv".

In that oval block, type in "data.csv".

#### ~ tutorialhint
Watch out! The name of this file can only be 8 letters long, not counting ".csv". For example, the longest name you could give it is "EnvData1.csv".

If you try to go longer, say "EnvironmentalData1.csv", it will cut off everything between the 8th letter and .csv, making it "Environm.csv".
```blocks
gatorLog.begin()
gatorEnvironment.beginEnvironment()
gatorLog.openFile("<YourLastName>ClassroomEnvData.csv")
```

## Step 5
The last block in ``||basic:on start||`` requires two parts; we will discuss each individually.

First, let us figure out how we will write a line of data into the file. In GatorLog, drag the ``||gatorLog:write line " " to current file||`` into the bottom of ``||basic:on start||``.

Thinking of our data like a spreadsheet, this translates to writing one row of data cells to our file.

## Step 6
As we are going to save three different oval blocks of data in a single row, we need a way to put all of those into the ``||GatorLog:write line||`` open space. To do this, we will use the ``||Text:join||`` block, which can be found in **Advanced** -> ``||Text:Text||``.

``||Text:Join||`` will take in multiple oval blocks and make them into one long line, which can be used in the ``||GatorLog:write line||`` block.

For this block, we want to give titles to the data we are going to store! As we are saving 3 different values separated by commas, we will need to ``||Text:join||`` 5 ovals (they need to be separated by commas!); that would be 1. <"Temperature (F)"> ; 2. <","> ; 3. <"Humidity"> ; 4. <","> ; 5. <"VOCs">

#### ~ tutorialhint
Don't forget, you need to separate the values by commas! That's what tells the .csv to go to the next cell in the spreadsheet. This ``||Text:join||`` needs to have the following:
```blocks
gatorLog.writeLine("Temperature (F)" + "," + "Humidity" + "," + "VOCs")
```
Don't worry if the join is horizontal or vertical, it doesn't matter!

## Step 7
We're done with our ``||basic:on start||``! Now, let's actually record some data!

Important question: what event are we going to use? For fun, let's use a new event! Look at the ``||Loops:Loops||`` drawer and pull out the event within.

This event, called the ``||Loops:every __ ms||``, executes the code blocks inside the event after a certain amount of time. This is perfect for us, it will help us record data at regular intervals! Let's make it ``||Loops:every 500 ms||``, which translates to twice every second.

## Step 8
Now, let's put a block to write data to a file in our ``||Loops:every||`` event.

Right click on your ``||GatorLog:write line||`` block in ``||basic:on start||`` and duplicate it. This will make it easy for us!

Move this duplicated block to your ``||Loops:every 500 ms||`` event. Instead of the names of the data, let's actually put the data values in from ``||GatorEnvironment:GatorEnvironment||``.

I'll leave that to you; you've seen these blocks before!

#### ~ tutorialhint
Take a look into the ``||GatorEnvironment:GatorEnvironment||`` drawer!

```blocks
loops.everyInterval(500, function () {
    gatorLog.writeLine("" + gatorEnvironment.getMeasurement(measurementType.degreesF) + "," + gatorEnvironment.getMeasurement(measurementType.humidity) + "," + gatorEnvironment.getMeasurement(measurementType.TVOC))
})
```

## Step 9
We're done with the code! Let's download this code and start recording data. Place the micro SD card into the gator:log and plug in your battery pack to your gator:bit. Be sure to use the big one that uses AA batteries!

If everything is working properly, you should see a small blue light on the gator:log blink every half of a second. If it isn't working, double check the [wiring tutorial.](https://learn.sparkfun.com/tutorials/sparkfun-gatorlog-hookup-guide/all#hardware-assembly)

Record data for a minute or two, and feel free to breathe on the sensor after a few seconds to make the values change!

#### ~ tutorialhint
Make sure that the gator:log has an SD card in it and the wiring is correct! We will be getting the file from the SD Card next.

## Step 10
Now that we have our data, lets plug the SD card into your computer using the adapter in your gator:science kit.

Confirm that your file exists and open it in Google Sheets. You should see hundreds of lines of data, starting with our title row of "Temerature (F),Humidity,VOCs".

## Step 11
You're finished collecting your data! Now head back to the slides, we're going to visualize this data!

```ghost
gatorLog.begin()
gatorLog.openFile("fileName.csv")
gatorEnvironment.beginEnvironment()
gatorLog.writeLine("Temperature (F)" + "," + "Humidity" + "," + "VOCs")
loops.everyInterval(500, function () {
    gatorLog.writeLine("replace with temperature" + "," + "replace with humidity" + "," + "replace with VOCs")
})
```

```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
gatorLog=github:sparkfun/pxt-gator-log
```
