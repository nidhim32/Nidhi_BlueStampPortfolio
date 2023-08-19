# UV Detecting Sunscreen Reminder Hat
This is a hat that contains a wearable UV sensor which works with Adafruit's FLORA circuit board to give you a reminder on when you should reapply your sunscreen for effecient protection. When you are outside under the sun, the UV sensor is able to detect the when the UV index is greater than the UV threshold. Once this criteria has been hit, the buzzer goes off which is your sign to reapply.

```HTML 

```

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Nidhi M | Dougherty Valley High School | Mechanical Engineering | Incoming Freshman


![Headstone image](headshot.jpeg)
Hi! My name is Nidhi and I am a rising freshman with an interest in mechanical engineering. This is my first project that I get to share with everyone here at BlueStamp and I have learned so much in the little time that I've been here. There were some challenges I faced throughout this project, however overcoming them was the most rewarding part of the process. 
# Final Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/IZJZI0BgFSU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

My final milestone consisted of the modifications that I made to the hat. First, I included a battery pack to the back of the hat so that it would be easier to access because you wouldn't have to connect it to your computer. Later, I chnaged the sound that the buzzer was making. Previously a song from mario kart was playing which I later adjusted through the code.


# Second Milestone



<iframe width="560" height="315" src="https://www.youtube.com/embed/8_MRZ_VAjxc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



My second milestone was getting all of my parts from the breadboard and moving them onto my actual hat. I also had to replace the arduino sensor with the FLORA which meant that the code had to be modified. I used conductive thread to sew everything together and make the connections. I ran into a problem where the buzzer's sounded muffled and quiet, however I overcame this by re-sewing each of the buzzer's legs to the FLORA and making sure that the thread was secure to both parts. The end result was the buzzer being sounded at a good volume.

# First Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/SDwStuIfWPI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



My first milestone was getting my arduino, UV sensor, and buzzer connected on my breadboard. They were able to connect to my computer through a micro-USB cable and send the correct signals to my serial moniter that the UV threshold had been reached or when the buzzer had been sounded.


# Code
//#include <Wire.h>
//#include "Adafruit_SI1145.h"

//dafruit_SI1145 uv = Adafruit_SI1145();

//tones for reminder tune
#define toneC    1911
#define toneC1    1804
#define toneD    1703
#define toneEb    1607
#define toneE    1517
#define toneF    1432
#define toneF1    1352
#define toneG    1276
#define toneAb    1204
#define toneA    1136
#define toneBb    1073
#define toneB    1012
#define tonec       955
#define tonec1      902
#define toned       851
#define toneeb      803
#define tonee       758
#define tonef       716
#define tonef1      676
#define toneg       638
#define toneab      602
#define tonea       568
#define tonebb      536
#define toneb       506
#define tonep       0 
int speaker = 3; // piezo wired to FLORA TX; D1 on arduino


uint32_t sinceTime = 0;
uint32_t markerTime;
boolean shouldChime = false;
uint16_t UVindex;
uint8_t UVthreshold = 150;
uint32_t reapplyInterval = 10000; // 15 minutes = 900000 milliseconds. One hour = 3600000 milliseconds. Two hours = 7200000 milliseconds

void setup() {
  pinMode(speaker, OUTPUT);
  Serial.begin(9600);
  // Serial.println("Adafruit SI1145 test");
  // if (! uv.begin()) {
  //   Serial.println("Didn't find Si1145");
  //   while (1);
  // }
  // Serial.println("OK!");
  resetTimer();
}

void loop() {
  Serial.println("===================");
  //UVindex = uv.readUV(); 
  //UVindex /= 100.0; // the index is multiplied by 100 so to get the integer index, divide by 100!  
  UVindex = analogRead(7); //read from analog pin D7 on FLORA; need to change to [A0, A5] for R3 board
  Serial.print("UV: ");  Serial.println(UVindex);
  Serial.print("Seconds until next alert: ");  Serial.println((reapplyInterval-sinceTime)/1000);
  delay(1000);
  
  sinceTime = millis()-markerTime;
  
  if (UVindex > UVthreshold && shouldChime){ //only chime when we are currently outside
    chime();
    Serial.println("===================");
    Serial.println("CHIME");
    shouldChime = false;
    resetTimer();
  }
  if (sinceTime > reapplyInterval) { //check to see if we've exceeded the time limit
    shouldChime = true;
    //resetTimer(); 
  }
  
}

void resetTimer(){
  markerTime = millis();
  sinceTime = 0;
}

void chime(){
int melody[] = {tonea, toneG, tonef, tonea, toneB, toneBb, tonee, toneG, toneF, toneg, toneg, tonef, toneg, tonee, toneg, tonea, tonea, tonea, toneB, toneBb, tonee, toneG, toneF, toneg, toneg,};
int rhythm[] = {12, 18, 18, 12, 12, 6, 12, 8, 8, 18, 12, 6, 12, 12, 6, 10, 6, 6, 12, 8, 8, 18, 12};
long vel = 20000;

for (int i=0; i<17; i++) {
    int note = melody[i];
    int tempo = rhythm[i];
 
    long tvalue = tempo * vel;
 
    //tocar(note, tvalue);
    long tempo_progress = 0;
  while (tempo_progress < tvalue) {
    digitalWrite(speaker, HIGH);
    delayMicroseconds(note / 2);
 
    digitalWrite(speaker, LOW);
    delayMicroseconds(note/2);	 
    tempo_progress += note;
  }
 
    delayMicroseconds(1000);
  }

}
# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| UV Sensor | To sense the UV | $11.69 | <div class="iframely-embed"><div class="iframely-responsive" style="height: 140px; padding-bottom: 0;"><a href="https://www.amazon.com/Comimark-UVM-30A-Ultraviolet-Detection-Arduino/dp/B07V3PW4R2/ref=sr_1_1?crid=2Q8OCQE12Y2N2" data-iframely-url="//iframely.net/bP6QAwT?card=small"></a></div></div><script async src="//iframely.net/embed.js"></script> |
| FLORA circuit board | Wearable micro-controller | $18.77 | <div class="iframely-embed"><div class="iframely-responsive" style="height: 140px; padding-bottom: 0;"><a href="https://www.amazon.com/FLORA-Wearable-electronic-platform-Arduino-compatible/dp/B00GLSRBLQ/ref=sr_1_3?crid=1B2ZS8IBDS4KB" data-iframely-url="//iframely.net/ktLE7cC?card=small"></a></div></div><script async src="//iframely.net/embed.js"></script> |
| Piezo buzzer | To make a sound reminding you to reapply your sunscreen | $7.99 | <div class="iframely-embed"><div class="iframely-responsive" style="height: 140px; padding-bottom: 0;"><a href="https://www.amazon.com/a15091400ux0103-Electronic-Mounting-Passive-Sounder/dp/B018I1WBNQ/ref=sr_1_6?crid=J4M8HAPZ1CK1" data-iframely-url="//iframely.net/GbgH1cD?card=small"></a></div></div><script async src="//iframely.net/embed.js"></script> |
| Conductive thread | To physically and electrically connect the parts | $10.99 | <div class="iframely-embed"><div class="iframely-responsive" style="height: 140px; padding-bottom: 0;"><a href="https://www.amazon.com/KOOKYE-Conductive-Bobbins-Sewable-Threader/dp/B07PFTXZLG/ref=sr_1_1_sspa?crid=3C1SEKB46OYOY" data-iframely-url="//iframely.net/Rt2E46F?card=small"></a></div></div><script async src="//iframely.net/embed.js"></script> |
| Mini sewing kit | To sew the parts to the hat | $4.59 | <div class="iframely-embed"><div class="iframely-responsive" style="height: 140px; padding-bottom: 0;"><a href="https://www.amazon.com/SINGER-01927-Travel-Sewing-Assorted/dp/B000YZ6CSA/ref=sr_1_8?crid=WPH9T9NFDGH0" data-iframely-url="//iframely.net/xXyypcr?card=small"></a></div></div><script async src="//iframely.net/embed.js"></script> |
| Power bank w/ USB | To power the FLORA circuit board | $17.99 | <div class="iframely-embed"><div class="iframely-responsive" style="height: 140px; padding-bottom: 0;"><a href="https://www.amazon.com/Attom-Tech-Portable-External-Emergency/dp/B07JZCZSH9/ref=sr_1_3?crid=2NQJCXAPTNELJ" data-iframely-url="//iframely.net/qp0GSkG?card=small"></a></div></div><script async src="//iframely.net/embed.js"></script> |
| Hat | To protect from the sun and used as the base for this project | $7.99 | <div class="iframely-embed"><div class="iframely-responsive" style="height: 140px; padding-bottom: 0;"><a href="https://www.amazon.com/dp/B0BYMQ4KQ6/ref=twister_B0BYMQ75B7?_encoding=UTF8" data-iframely-url="//iframely.net/JmdGpgV?card=small"></a></div></div><script async src="//iframely.net/embed.js"></script> |

