int soundSensor=A0;
int FAN=8;
boolean FANStatus=false;

void setup() {
 pinMode(soundSensor,INPUT);
 pinMode(FAN,OUTPUT);
 Serial.begin(9600);
}

void loop() {
 int Sensordata=analogRead(soundSensor);
 if(Sensordata>200){

  if(FANStatus==false){
     FANStatus=true;
     digitalWrite(FAN,HIGH);
  }
  else{
    FANStatus=false;
    digitalWrite(FAN,LOW);
  }
 }
 Serial.println(Sensordata);
 delay(100);
}
// นาย ณัฐพงษ์ วงศ์อินทร์ 
