# EXPERIMENT-NO--05-Distance measurement using Ultrasonic sensor

## AIM: 
To interface an ultrasonic pair and measure the distance in centimeters , calculate the error
 
### COMPONENTS REQUIRED:
1.	ultrasonic sensor module HC-SR04
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats do. It offers excellent non-contact range detection with high accuracy and stable readings in an easy-to-use package from 2 cm to 400 cm or 1” to 13 feet.

The operation is not affected by sunlight or black material, although acoustically, soft materials like cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications
Power Supply − +5V DC
Quiescent Current − <2mA
Working Current − 15mA
Effectual Angle − <15°
Ranging Distance − 2cm – 400 cm/1″ – 13ft
Resolution − 0.3 cm
Measuring Angle − 30 degree

The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:

The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz).
The sound travels through the air. If it finds an object, it bounces back to the module.
The ultrasound receiver (echo pin) receives the reflected sound (echo).
The time between the transmission and reception of the signal allows us to calculate the distance to an object. This is possible because we know the sound’s velocity in the air. Here’s the formula:

distance to an object = ((speed of sound in the air)*time)/2
speed of sound in the air at 20ºC (68ºF) = 343m/s

### FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR 


![image](https://user-images.githubusercontent.com/36288975/166430594-5adb4ca9-5a42-4781-a7e6-7236b3766a85.png)


## FIGURE 02:
![Screenshot 2024-03-08 211059](https://github.com/nithish467/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/150232274/b253d91b-ab02-4225-b8cf-79fe07ef8950)

## FIGURE 03:
![Screenshot 2024-03-08 211139](https://github.com/nithish467/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/150232274/6fff268a-87fe-40d1-b788-7c7edeecb708)

## SCHEMATIC DIAGRAM:

![Screenshot 2024-03-08 212634](https://github.com/nithish467/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/150232274/83c63a69-68c9-49b9-92b0-5cb83dab8b48)


### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 
```
int echopin=6;
int trigpin=7;
int red=9;
int green=8;
long duration;
float distance;

void setup()
{
  pinMode(echopin,INPUT);
  pinMode(trigpin,OUTPUT);
  pinMode(red,OUTPUT);
  pinMode(green,OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  digitalWrite(trigpin, LOW);
  delay(10); 
  digitalWrite(trigpin, HIGH);
  delay(10);
  digitalWrite(trigpin, LOW);
  duration=pulseIn(echopin,HIGH);
  distance=duration*0.034/2;
  Serial.print("distance=");
  Serial.print(distance);
  Serial.println("cms");
  
  if(distance>50)
  {
    digitalWrite(green, HIGH);
  delay(500);
   digitalWrite(green, LOW);
  delay(500);
    }
  else
  {
    digitalWrite(red, HIGH);
  delay(500);
    digitalWrite(red, LOW);
  delay(500);
  }
  
}
```





### Distance vs measurement table :

![Screenshot 2024-03-08 212717](https://github.com/nithish467/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/150232274/7048f6e8-2a75-428f-994a-29b07e041700)


![Screenshot 2024-03-08 212732](https://github.com/nithish467/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/150232274/f263e916-e407-48b0-9656-92e5ed56a542)
			
 
			
			
			

			
			
			
			
			
			Average error = sum/ number of readings 
 








### RESULTS



 
