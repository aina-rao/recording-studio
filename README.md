# recording-studio
#define REC 2
#define PLAY_E 3
#define FT 5
#define playTime 5000
#define recordTime 3000
void setup() 
{
 pinMode(REC,OUTPUT);
 pinMode(PLAY_E,OUTPUT);
 pinMode(FT,OUTPUT);
 Serial.begin(9600);
}
void loop() {
   while (Serial.available() > 0) {
         char inChar = (char)Serial.read();
           if(inChar =='p' || inChar =='P'){
           digitalWrite(PLAY_E, HIGH);
           delay(50);
           digitalWrite(PLAY_E, LOW);  
             Serial.println("Playbak Started");  
           delay(playTime);
             Serial.println("Playbak Ended");
           break; 
           }       
           else if(inChar =='r' || inChar =='R'){
             digitalWrite(REC, HIGH);
             Serial.println("Recording started");
             delay(recordTime);
             digitalWrite(REC, LOW);
             Serial.println("Recording Stopped ");              
           } 
                         
     Serial.println("###Serial Monitor Exited");      
   }
Serial.println("### Enter r to record, p to play");
 delay(500);
}
