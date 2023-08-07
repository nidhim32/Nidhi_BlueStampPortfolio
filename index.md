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

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**


For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone



<iframe width="560" height="315" src="https://www.youtube.com/embed/8_MRZ_VAjxc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



My second milestone was getting all of my parts from the breadboard and moving them onto my actual hat. I also had to replace the arduino sensor with the FLORA which meant that the code had to be modified. I used conductive thread to sew everything together and make the connections. I ran into a problem where the buzzer's sounded muffled and quiet, however I overcame this by re-sewing each of the buzzer's legs to the FLORA and making sure that the thread was secure to both parts. The end result was the buzzer being sounded at a good volume.

# First Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/SDwStuIfWPI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



My first milestone was getting my arduino, UV sensor, and buzzer connected on my breadboard. They were able to connect to my computer through a micro-USB cable and send the correct signals to my serial moniter that the UV threshold had been reached or when the buzzer had been sounded.

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| UV Sensor | To sense the UV | $11.69 | https://www.amazon.com/Comimark-UVM-30A-Ultraviolet-Detection-Arduino/dp/B07V3PW4R2/ref=sr_1_1?crid=2Q8OCQE12Y2N2&keywords=uv+sensor+arduino&qid=1691435040&sprefix=UV+Sensor%2Caps%2C157&sr=8-1 |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
