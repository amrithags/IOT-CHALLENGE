# IOT-CHALLENGE
# IOTLevel-1
> My name is Amritha G S. I am studying BTech (Bachelor of Technology)in Electrical and Electronics Engineering Final Year <br>
> at Trinity College of Engineering,Trivandrum .
>
>  The following are the IOT experiments and assignments I have done as part of the Kerala IOT<br> 
>  challenge LEVEL-1


## EXPERIMENT 1 - HELLO WORLD LED BLINKING

### Components required

 - Arduino UNO Board
 - USB Cable
 - LED
 - 220 ohm Resistor
 - breadboard
 - Jumper wires

![hello world](https://user-images.githubusercontent.com/81356075/144737649-696fe82d-fa96-4454-b737-6b0d77035bfb.png)

### CODE
  
```
void setup()
{
  pinMode(8, OUTPUT);
}

void loop()
{
  digitalWrite(8, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(8, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
} 

```

## EXPERIMENT 2 - TRAFFIC LIGHT

### Components required

 - Arduino UNO Board
 - USB Cable
 - LED-red,yellow,green
 - 220 ohm Resistor * 3
 - breadboard
 - Jumper wires

![traffic](https://user-images.githubusercontent.com/81356075/144737815-8afb2455-a61a-4e3d-9c52-ac0188837366.png)

### CODE

```
int redled =10; // initialize digital pin 8.
int yellowled =7; // initialize digital pin 7.
int greenled =4; // initialize digital pin 4.
void setup()
{
pinMode(redled, OUTPUT);// set the pin with red LED as “output”
pinMode(yellowled, OUTPUT); // set the pin with yellow LED as “output”
pinMode(greenled, OUTPUT); // set the pin with green LED as “output”
}
void loop()
{
digitalWrite(greenled, HIGH);//// turn on green LED
delay(5000);// wait 5 seconds

digitalWrite(greenled, LOW); // turn off green LED
for(int i=0;i<3;i++)// blinks for 3 times
{
delay(500);// wait 0.5 second
digitalWrite(yellowled, HIGH);// turn on yellow LED
delay(500);// wait 0.5 second
digitalWrite(yellowled, LOW);// turn off yellow LED
} 
delay(500);// wait 0.5 second
digitalWrite(redled, HIGH);// turn on red LED
delay(5000);// wait 5 seconds
digitalWrite(redled, LOW);// turn off red LED
}

``` 

## EXPERIMENT 3 - LED CHASING EFFECT

### Components required

 - Arduino UNO Board
 - USB Cable
 - LED * 6
 - 220 ohm Resistor * 6
 - breadboard
 - Jumper wires

![led chasing](https://user-images.githubusercontent.com/81356075/144737806-fffd5408-7818-4d8f-9207-185049eb088a.png)
  
### CODE
```
int BASE = 2 ;  // the I/O pin for the first LED
int NUM = 6;   // number of LEDs
void setup()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     pinMode(i, OUTPUT);   // set I/O pins as output
   }
}
void loop()
{
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, LOW);    // set I/O pins as “low”, turn off LEDs one by one.
     delay(200);        // delay
   }
   for (int i = BASE; i < BASE + NUM; i ++) 
   {
     digitalWrite(i, HIGH);    // set I/O pins as “high”, turn on LEDs one by one
     delay(200);        // delay
   }  
}

``` 

## EXPERIMENT 4 - BUTTON CONTROLLED LED

### Components required

 - Arduino UNO Board
 - Button switch
 - USB Cable
 - Red m5 LED
 - 220 ohm Resistor
 - 10 K ohm Resistor
 - breadboard
 - Jumper wires
  
![button controlled](https://user-images.githubusercontent.com/81356075/144737823-1997e1f6-c355-4db4-a2f8-05a0ecc18a08.png)

### CODE

```
int ledpin=11;// initialize pin 11
int inpin=7;// initialize pin 7
int val;// define val
void setup()
{
pinMode(ledpin,OUTPUT);// set LED pin as “output”
pinMode(inpin,INPUT);// set button pin as “input”
}
void loop()
{
val=digitalRead(inpin);// read the level value of pin 7 and assign if to val
if(val==LOW)// check if the button is pressed, if yes, turn on the LED
{ digitalWrite(ledpin,LOW);}
else
{ digitalWrite(ledpin,HIGH);}
}

``` 

## EXPERIMENT 5 - BUZZER

### Components required

 - Arduino UNO Board
 - Buzzer
 - USB Cable
 - breadboard
 - Jumper wires

![buzzer](https://user-images.githubusercontent.com/81356075/144737792-1a685928-7cda-4ad8-bcd5-c1a5d13bcbe6.png)

### CODE
  
```
int buzzer=8;// initialize digital IO pin that controls the buzzer
void setup() 
{ 
  pinMode(buzzer,OUTPUT);// set pin mode as “output”
} 
void loop() 
{
digitalWrite(buzzer, HIGH); // produce sound
}

``` 

## EXPERIMENT 6 - RGB LED
### Components required

 - Arduino UNO Board
 - USB Cable
 - RGB LED
 - 220 ohm Resistor * 3
 - breadboard
 - Jumper wires

![rgb led](https://user-images.githubusercontent.com/81356075/144737814-53f2dd40-c605-4c12-962b-655809e3cc1d.png)

### CODE
  
```
int redpin = 11; //select the pin for the red LED
int bluepin =10; // select the pin for the blue LED
int greenpin =9;// select the pin for the green LED
int val;
void setup() {
  pinMode(redpin, OUTPUT);
  pinMode(bluepin, OUTPUT);
  pinMode(greenpin, OUTPUT);
  Serial.begin(9600);
}
void loop() 
{
for(val=255; val>0; val--)
  {
   analogWrite(11, val);
   analogWrite(10, 255-val);
   analogWrite(9, 128-val);
   delay(1); 
  }
for(val=0; val<255; val++)
  {
   analogWrite(11, val);
   analogWrite(10, 255-val);
   analogWrite(9, 128-val);
   delay(1); 
  }
 Serial.println(val, DEC);
}

``` 

## EXPERIMENT 7 - LDR LIGHT SENSOR

### Components required

 - Arduino UNO Board
 - USB Cable
 - Photo Resistor
 - Red LED
 - 220 ohm Resistor
 - 10 K ohm Resistor
 - breadboard
 - Jumper wires

![ldr light](https://user-images.githubusercontent.com/81356075/144737801-0ea2afc6-aaa0-463f-86dc-c793a6015059.png)

### CODE
  
```
int potpin=0;// initialize analog pin 0, connected with photovaristor
int ledpin=11;// initialize digital pin 11, 
int val=0;// initialize variable val
void setup()
{
pinMode(ledpin,OUTPUT);// set digital pin 11 as “output”
Serial.begin(9600);// set baud rate at “9600”
}
void loop()
{
val=analogRead(potpin);// read the value of the sensor and assign it to val
Serial.println(val);// display the value of val
analogWrite(ledpin,val/4);// set up brightness（maximum value 255）
delay(10);// wait for 0.01 
}

```
 
## EXPERIMENT 8 - FLAME SENSOR

### Components required

 - Arduino UNO Board
 - USB Cable
 - Flame Sensor
 - Buzzer
 - 10 k ohm Resistor
 - breadboard
 - Jumper wires

![flame sensor](https://user-images.githubusercontent.com/81356075/144737795-26c16c32-ba0a-4299-b319-e8bda9262224.png)

### CODE
  
```
int flame=0;// select analog pin 0 for the sensor
int Beep=9;// select digital pin 9 for the buzzer
int val=0;// initialize variable
 void setup() 
{
  pinMode(Beep,OUTPUT);// set LED pin as “output”
 pinMode(flame,INPUT);// set buzzer pin as “input”
 Serial.begin(9600);// set baud rate at “9600”
 } 
void loop() 
{ 
  val=analogRead(flame);// read the analog value of the sensor 
  Serial.println(val);// output and display the analog value
  if(val>=600)// when the analog value is larger than 600, the buzzer will buzz
  {  
   digitalWrite(Beep,HIGH); 
   }else 
   {  
     digitalWrite(Beep,LOW); 
    }
   delay(500); 
}

``` 
 
## EXPERIMENT 9-LM35 TEMPERATURE SENSOR

### Components required

 - Arduino UNO Board
 - LM35 
 - USB Cable
 - breadboard
 - Jumper wires

![lm35](https://user-images.githubusercontent.com/81356075/144737807-668c354a-7a1f-4469-883f-09e0149ceb2a.png)

### CODE
  
```
int potPin = 0; // initialize analog pin 0 for LM35 temperature sensor
void setup()
{
Serial.begin(9600);// set baud rate at”9600”
}
void loop()
{
int val;// define variable
int dat;// define variable
val=analogRead(0);// read the analog value of the sensor and assign it to val
dat=(125*val)>>8;// temperature calculation formula
Serial.print("Tep");// output and display characters beginning with Tep
Serial.print(dat);// output and display value of dat
Serial.println("C");// display “C” characters
delay(500);// wait for 0.5 second
}
