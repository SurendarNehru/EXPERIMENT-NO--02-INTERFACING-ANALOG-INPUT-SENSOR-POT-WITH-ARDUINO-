 ##INTERFACING-ANALOG-INPUT-SENSOR-POT-WITH-ARDUINO-

##DATE :23/02/2024
##NAME : Surendar N
##ROLLNUMBER : 212222040165
##DEPARTMENT : Computer Science and Engineering



**AIM**:  To interface a Analog  input (angular displacement sensor POT) and scale the values up on change in the input.


**COMPONENTS REQUIRED:**
1.	10 KΩPOT
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 
6.	LED of choice 
**


**THEORY**: 

**Analog signals:**

Analog signals – directly measurable quantities in terms of some other quantity.
Examples:
1. Thermometer – mercury height rises as temperature rises
2. Car Speedometer – Needle moves farther right as you accelerate
3. Stereo – Volume increases as you turn the knob
Reason for conversion of analog to digital quantity is that as the controller or any microprocessor works with digital signals in the form of 0 and 1s, in order to make the signal compatible  most of the analog signals are converted into its equivalent digital level signals using an analog to digital converter .
Quantizing - breaking down analog value is a set of finite states
Encoding - assigning a digital word or number to each state and matching it to the input signal
 There are two ways to best improve accuracy of A/D conversion:
Increasing the resolution which improves the accuracy in measuring the amplitude of the analog signal.
Increasing the sampling rate which increases the maximum frequency that can be measured.
General specifications of analog sensor
	1. Range
	2. Accuracy
	3.Linearity
	4.Compatiblity
	5. signal conversion capability

**Potentiometer**
A potentiometer, informally a pot, is a three-terminal resistor with a sliding or rotating contact that forms an adjustable voltage divider. If only two terminals are used, one end and the wiper, it acts as a variable resistor or rheostat.
Potentiometers are commonly used to control electrical devices such as volume controls on audio equipment. Potentiometers operated by a mechanism can be used as position transducers, for example, in a joystick. Potentiometers are rarely used to directly control significant power (more than a watt), since the power dissipated in the potentiometer would be comparable to the power in the controlled load
CIRCUIT DIAGRAM





![image](https://user-images.githubusercontent.com/36288975/163530788-eec3cdc3-95e8-4d2d-8349-6d0ea4c9439c.png)

![Screenshot 2024-02-23 160413](https://github.com/SurendarNehru/EXPERIMENT-NO--02-INTERFACING-ANALOG-INPUT-SENSOR-POT-WITH-ARDUINO-/assets/119476295/53a9ad9b-7cef-4105-916b-57e4b8ef1607)






**PROCEDURE:**

1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select your board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 



**PROGRAM** 
 int pot;
int led=7;
void setup()
{
  pinMode(led,OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  pot=analogRead(A0);
  //Serial.print("Value=");
  Serial.println(pot);
  if(pot>900)
  {
  digitalWrite(led,HIGH);
  delay(500); // Wait for 500 millisecond(s)
  digitalWrite(led,LOW);
  delay(500); // Wait for 500 millisecond(s)
}
  else
  {
    digitalWrite(led,LOW);
    delay(500);
  }
}


**
**Simulation output:** 



[My image](username.github.com/repository/img/image.jpg)

LIGHT CONDITION OFF:
![Screenshot 2024-02-23 161111](https://github.com/SurendarNehru/EXPERIMENT-NO--02-INTERFACING-ANALOG-INPUT-SENSOR-POT-WITH-ARDUINO-/assets/119476295/3c899cdd-0764-4d2b-8590-600c1f46b522)
LIGHT CONDITION ON:
![Screenshot 2024-02-23 161146](https://github.com/SurendarNehru/EXPERIMENT-NO--02-INTERFACING-ANALOG-INPUT-SENSOR-POT-WITH-ARDUINO-/assets/119476295/33a11b11-30cd-461f-bfc6-2aaa0f4d2462)
SERIAL MONITOR GRAPH:
![Screenshot 2024-02-23 155534](https://github.com/SurendarNehru/EXPERIMENT-NO--02-INTERFACING-ANALOG-INPUT-SENSOR-POT-WITH-ARDUINO-/assets/119476295/80559a6b-a5b3-4af8-867f-555f797bace9)









**RESULT: ** Arduino uno analog input functioning is learned and interfaced with digital input switch .
