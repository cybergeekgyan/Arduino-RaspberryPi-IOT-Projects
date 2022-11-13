# Water-pH-Monitoring
Sense the water pH of a hydroponic plant with Arduino Nano 33 BLE Sense and determine if it's right using an Edge Impulse trained model.

## Hardware Components

- Arduino Nano 33 BLE Sense ×	1	
- standard ph probe ×	1	
- pH sensor ×	1	
- LED (generic) ×	3	
- Resistor 220 ohm ×	3	

## Software apps and online services

- Arduino IDE	

- Edge Impulse Studio	

## Setup

---**Hardware**---

For this project I decided to use Arduino Nano 33 BLE Sense as the central unit, since I've used it in the HarvardX TinyML course. 
 
 - The circuit is simple: 
   - a pH sensor (with a water pH probe connected with it) is wired to an Arduino analog input and 3 leds are driven as digital outputs. 
   - After I uploaded the sketch to the Arduino, I had to calibrate the sensor. 
   - I dipped a pH indicator paper in a glass of tap water to know its pH, and it was 7. 
   - Then, I dipped the probe in the same glass and I adjusted the sensor trimmer close to the probe connector until I read values around 7 on the serial monitor. 
   - For the specifc sensor I've used, it was usefull adjust also the trimmer close to the sensor pins, to improve the sensibility. 
   - For this project I chose three pH edge values:

- pH 4: pH values lower then 5 is too low for the plant

- pH 5: pH values from 5 to 6 are optimal for the plant

- pH 7: pH values around 7 is too high for the plant

To have a solution with pH 4, I've put some lemon juice in the glass of tap water and then I've measured the pH with the indicator paper to verify that it was around 4, so I dipped the probe in the glass and it sensed values around 4, that made me sure that the sensor was well calibrated. 

- For the pH 5 solution, I took another glass of tap water and I put in it a pH corrector to reduce its pH. 
- Both the indicator paper and the pH sensor showed a value around 5, so I decided to use this solution for the hydroponic plant. 
- The three leds in the circuits indicates the pH level:

- red led: turns on when pH value is around 4

- green led: turns on when pH value is around 5

- yellow led: turns on when pH value is around 7


## On the Arduino IDE

To include the model library in the Arduino IDE,

- I went on Sketch -> Include Library -> Add.ZIP, 
- then I included the library in my sketch and add few lines to the code in order to run the model to the Arduino Nano 33 BLE Sense.

