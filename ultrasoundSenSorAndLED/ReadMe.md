# ultrasound SenSor And LED

### # material

- 1 LED (RGB)
- 1 ultrasound SenSor



### # circuit & theory 

- 



### # video



### # code

```c
#define TRIG 2
#define ECHO 3
#define RED 11
#define GREEN 10
#define BLUE 9


void setup(){
  pinMode(TRIG, OUTPUT);
  pinMode(ECHO, INPUT);
}

void loop(){
  // takes phyical time to turn on, off ->calibration
  digitalWrite(TRIG,LOW);
  delayMicroseconds(2);
  digitalWrite(TRIG,HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG,LOW);
  
  // ultrawave distance to Centimeter
  // check ultrawave distance of pin2 when its high
  long distance = (pulseIn(ECHO,HIGH)) / 58.2;
  
  
  //LED off
  analogWrite(RED,0);
  analogWrite(GREEN,0);
  analogWrite(BLUE,0);
  
  //change color according to distance
  if(distance < 10){
    analogWrite(RED,255);
  }else if(distance < 20){
    analogWrite(GREEN,255);
  }else if(distance < 30){
    analogWrite(BLUE,255);
  }
  
  delay(100);
  

}
```



