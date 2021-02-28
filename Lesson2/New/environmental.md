# Collecting Temperature Data with the Environmental Sensor
### @explicitHints true
 
## Step 1
 
We are going to learn how to use a micro:bit and gator:bit environmental sensor  to display temperature values - Vamos a aprender a usar un sensor ambiental micro:bit y gator:bit para mostrar los valores de temperatura.
 
Submit your answers using the google form linked on [this page](https://schoolwidelabs.github.io/sensor-immersion/assessments/Lesson2/environmental_assessment.html) under your teacher's name. - Envíe sus respuestas utilizando el formulario de Google vinculado en [esta página](https://schoolwidelabs.github.io/sensor-immersion/assessments/Lesson2/environmental_assessment.html) bajo el nombre de su profesor.
 
```template
input.onButtonPressed(Button.A, function () {
    
})
```
 
## Step 2
 
**Before you begin, answer question 1 on the google form - Antes de comenzar, responda la pregunta 1 en el formulario de Google**

Describe your plan for getting the microbit to display the temperature values - 
Describe tu plan para que el microbit muestre los valores de temperatura
 
If you need help with wiring, take a look at [these guides.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing) - 
Si necesita ayuda con el cableado, consulte [estas guías.](https://docs.google.com/document/d/1KrhVLl_owwXz_xAVbcIEAG9O5N4wdBY3mjd-GX34Bag/edit?usp=sharing)
 
## Step 3
 
To start, use the GatorEnvironment ``||gatorEnvironment: initialize||`` command. Start the sensor when the ``||basic: program starts||`` - 
Para comenzar, use el mandato, GatorEnvironment ``||gatorEnvironment: initialize||``. Inicie el sensor con ``||basic: inicia el programa||``
 
## Step 4
 
Use the ``||basic:showNumber||`` and ``||gatorEnvironment.get||`` commands to show the temperature on the micro:bit. Make sure to ``||Math: round||`` 
so you can read the number on the micro:bit. - Utilice las mandato, ``||basic: monstrar número||`` y ``||gatorEnvironment.get||`` para mostrar la temperatura en el micro: bit. Asegúrese de `` || Math: dedondeo || `` para que pueda leer el número en el micro:bit.
 
 
#### ~ tutorialhint
 
Rounding makes the value easier to read on the display. - El redondeo facilita la lectura del valor en la pantalla.

Instead of seeing 72.9999999999, you just see 73. - En lugar de ver 72.9999999999, solo ve 73.
 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF)))
})
 
```
 
## Step 5
Great! You did it. Now you can test it out. How could you use the Math buttons to change the display to two times the temperature? Would you round before or after you double the temperature? - ¡Excelente! Lo hiciste. Ahora puedes probarlo. ¿Cómo podría usar los botones matemáticos para cambiar la pantalla a dos veces la temperatura? ¿Lo redondearías antes o después de doblar la temperatura?
 
**Don't forget to fill out the final questions on the google form. - 
No olvide completar las preguntas finales en el formulario de Google.**
 
```ghost
input.onButtonPressed(Button.A, function () {
    basic.showNumber(Math.round(gatorEnvironment.getMeasurement(measurementType.degreesF) * 2))
})
gatorEnvironment.beginEnvironment()
```
 
```package
gatorEnvironment=github:sparkfun/pxt-gator-environment#v1.0.13
```
