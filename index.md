# WALL-E Robot: An Interactive Companion

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
|Anish N| Dougherty Valley High School | Computer Engineering | Incoming Senior

<section id="abstract">
  <h2>Abstract</h2>
  <p>
    WALL-E is an interactive, emotive robot designed as a personalized companion, capable of reacting to human gestures through proximity sensing and emotion simulation. The goal of this project is to create a robot that fosters human-robot interaction by providing emotional feedback using non-verbal cues such as facial expressions, head movements, and messages on an LCD screen. By using an Arduino Uno, servos, ultrasonic sensors, and a mobile app, WALL-E can respond to user proximity with different emotions.
  </p>
  <p>
    The potential applications of WALL-E extend beyond simple companionship. Specifically, it can serve as a communication tool for individuals who face difficulties in expressing emotions, such as those with alexithymia. The integration of servo motors to mimic facial expressions, LED matrices to simulate eye movements, and an LCD screen to convey messages allows for an immersive emotional experience without requiring verbal interaction. This project contributes to the broader field of affective computing by combining robotics, sensor technology, and human-centered design.
  </p>
  <p>
    This portfolio documents the hardware and software development process, challenges encountered, and future opportunities for enhancing WALL-E’s capabilities to better serve its intended purpose as an emotional support companion.
  </p>
</section>

**Important skills learned**
-Soldering, Dremeling, Arduino programming, Ultrasonic sensor integration, Remote control system developement, App development and design, Wireless communication, Servo integration, Electrical wiring

<section id="introduction">
  <h2>Introduction</h2>
  <p>
    Human interaction with technology is rapidly evolving, with emotional engagement playing an increasingly important role in improving the human experience. Emotional robots, which are capable of detecting, processing, and responding to user behavior, have seen growing applications in healthcare, therapy, and education. The ability for machines to convey empathy or simulate emotions allows for unique, non-verbal interaction models that can serve people who have limited means of traditional communication.
  </p>
  <p>
    The motivation for developing WALL-E stems from the idea of integrating technology into our daily lives in a way that not only provides utility but also enhances emotional well-being. WALL-E was designed to be a friendly companion that can recognize human gestures and respond with different emotional states. The inspiration for this project comes from exploring how emotionally intelligent robotics can offer supportive roles in people's lives, specifically by making human-robot interaction accessible and intuitive.
  </p>
  <p>
    This project brings together a combination of hardware and software components, with an emphasis on emotional communication through movement, visual cues, and reactive expressions. Utilizing ultrasonic sensors, LED matrices, and servo motors, WALL-E is capable of responding to gestures with expressions that range from happiness to surprise. Additionally, a custom-built Android application adds further interaction options by enabling remote control.
  </p>
  <p>
    By creating an emotionally responsive robot, this project aims to show how technological advancements can go beyond the functional and instead create bonds that are both comforting and beneficial, particularly for those with barriers in expressing or understanding emotions. This document will take you through the process of building WALL-E, the decisions made during the development, the challenges faced, and how this robot represents a step forward in the field of affective robotics.
  </p>
</section>

<section id="methodology">
  <h2>2. Methodology</h2>
  
  <h3>2.1 Overview of Hardware Components</h3>
  <p>
    The WALL-E robot involves a variety of hardware components, each fulfilling a critical role in providing emotional interaction and physical movement. The key components used are described below:
  </p>
  <ul>
    <li><strong>Arduino Uno</strong>: Acts as the main control board, responsible for processing inputs from the various sensors and generating outputs to control the servos, LCD screen, and LED matrix.</li>
    <li><strong>Ultrasonic Sensor (HC-SR04)</strong>: Detects the user's proximity, enabling WALL-E to change its emotional expression depending on how close or far a user is.</li>
    <li><strong>LCD Screen (16x2)</strong>: Provides a text-based representation of WALL-E's emotional state, adding a layer of non-verbal communication to the interaction.</li>
    <li><strong>LED Matrix (8x8)</strong>: Represents different emotional states through changes in WALL-E's "eyes" by displaying different LED patterns, adding a layer of expressiveness.</li>
    <li><strong>Bluetooth Module (HC-05)</strong>: Connects WALL-E to a mobile device, allowing remote control through a custom-built Android app.</li>
    <li><strong>Servos</strong>: Control WALL-E's physical movements, such as head tilts and eyebrow movements, giving WALL-E dynamic responses based on different stimuli.</li>
  </ul>
  <figure>
    <img src="schematicwithbluetoothj_bb.png" alt="WALL-E Wiring Schematic">
    <figcaption>Figure 1: Wiring Schematic of WALL-E Robot</figcaption>
  </figure>

  <h3>2.2 Electrical Schematic and Wiring</h3>
  <p>
    The electrical schematic of WALL-E demonstrates the integration of all key components. The Arduino Uno acts as the hub, with each device connected to the appropriate power, ground, and signal pins.
  </p>
  <p>
    The <strong>HC-SR04 ultrasonic sensor</strong> was connected with its trigger pin and echo pin to digital pins on the Arduino, allowing distance measurements. The <strong>HC-05 Bluetooth module</strong> was connected through a voltage divider to match its 3.3V level, ensuring compatibility with the 5V output of the Arduino. The <strong>servos</strong> were wired to control head and eyebrow movement, providing expressiveness, and the <strong>LCD screen</strong> was connected to display messages.
  </p>

 <h3>2.3 Software Development</h3>

  <h4>2.3.1 Arduino Code for Emotions and Reactions</h4>
  <p>
    The Arduino code is the heart of WALL-E's functionality. It integrates sensor input, Bluetooth commands, and controls to provide appropriate physical responses.
  </p>
  <ul>
    <li><strong>Proximity Detection and Emotion Control</strong>: The <strong>HC-SR04 ultrasonic sensor</strong> measures the distance between the robot and an object. Based on distance thresholds, WALL-E changes its expressions accordingly.</li>
    <li><strong>LED Matrix Animation</strong>: Displays different eye patterns corresponding to particular emotional states.</li>
    <li><strong>LCD Screen Messages</strong>: Displays messages corresponding to emotional states.</li>
  </ul>
  <figure>
    <img src="logic.png" alt="Emotion Logic Flowchart">
    <figcaption>Figure 3: Logic Flowchart for Emotional Reactions</figcaption>
  </figure>

  <h4>2.3.2 Mobile Application for Remote Control</h4>
  <p>
    The <strong>Android application</strong> for remote control was built using MIT App Inventor. The app interface consists of buttons for different commands, such as "Head Up," "Turn Left," and different emotional modes like "Happy" or "Angry." The app communicates with the HC-05 Bluetooth module to send these commands to the Arduino.
  </p>
  <figure>
    <img src="appcode.png" alt="Android Application Design">
    <figcaption>Figure 4: Android Application Interface</figcaption>
  </figure>

  <h3>2.4 Challenges Encountered</h3>
  <ul>
    <li><strong>Bluetooth Connectivity Issues</strong>: Establishing consistent and reliable communication with the Bluetooth module required attention to voltage differences between Arduino pins and the HC-05.</li>
    <li><strong>Servo Calibration and Power Issues</strong>: The servos required fine calibration to avoid jerky movement, and improper grounding initially caused power issues.</li>
    <li><strong>Managing Concurrent Outputs</strong>: Synchronizing multiple outputs was a challenge. Efficient use of Arduino's timing functions ensured smooth operation.</li>
  </ul>
</section>

<section id="potential-applications">
  <h2>Potential Applications</h2>
  <p>
    WALL-E’s potential extends far beyond being a simple novelty item; it is envisioned as a meaningful tool in both personal and professional contexts. One of the core applications of WALL-E is as an emotional support companion, especially for individuals who struggle with expressing or interpreting emotions. This includes people with alexithymia, a condition where an individual has difficulty identifying and describing their own emotions. By providing non-verbal cues in response to gestures and proximity, WALL-E could assist these individuals by acting as a tangible reference point for learning about emotional responses.
  </p>
  <h3>3.1 Therapy and Emotional Support</h3>
  <p>
    Therapists could use WALL-E to facilitate emotional awareness exercises. The robot’s expressions could serve as visual aids during therapy sessions, helping patients understand how emotions are represented through physical movements. For example, WALL-E can react with sad expressions when approached too closely or display happiness when interacted with gently, thereby serving as a non-verbal medium that makes emotional recognition more intuitive. This capability has promising applications in treating conditions such as autism, where understanding social cues is often a challenge.
  </p>
  <h3>3.2 Education and Social Interaction</h3>
  <p>
    In educational settings, WALL-E could serve as an engaging way to teach emotional intelligence to children. Using a robot to teach children how to identify emotions provides a safe and interactive method for practicing social skills without the complexities and unpredictability of human interaction. Studies have shown that robots can significantly improve the learning experience by providing feedback that children perceive as non-threatening, thereby boosting their confidence and willingness to learn.
  </p>
  <h3>3.3 Companionship for the Elderly</h3>
  <p>
    The elderly, particularly those in assisted living facilities, could also benefit from a device like WALL-E. Emotional robots have been shown to reduce feelings of loneliness and provide companionship, and WALL-E's non-verbal emotional feedback can give the elderly a sense of interaction, even in environments with limited social opportunities. WALL-E’s simplistic yet engaging form of emotional connection makes it a potentially valuable tool in enriching the emotional lives of elderly individuals.
  </p>
  <h3>3.4 Affective Computing and Human-Robot Interaction</h3>
  <p>
    On a broader level, WALL-E serves as a prototype that contributes to the field of affective computing and human-robot interaction. Affective computing focuses on the development of systems that can recognize, process, and simulate human emotions. WALL-E represents how combining robotics, sensors, and user-centered design can result in a robot capable of real-time emotional feedback. Researchers could use WALL-E’s design as a basis for developing more sophisticated affective robots that bridge gaps in human-technology communication.
  </p>
</section>

<section id="future-work">
  <h2>Future Work</h2>
  <h3>4.1 Facial Recognition and User Personalization</h3>
  <p>
    A natural next step is to integrate facial recognition capabilities using a camera module. By incorporating computer vision, WALL-E could identify users and remember their past interactions, providing more personalized emotional responses. For example, WALL-E could recognize frequent users and offer a greeting or specific emotional response tailored to that individual. This feature would make WALL-E more engaging and relevant, adapting to the emotional needs of different individuals.
  </p>
  <h3>4.2 Voice Interaction and Natural Language Processing</h3>
  <p>
    Incorporating a voice interaction system would make WALL-E even more accessible. Using a simple microphone and speaker setup along with a Natural Language Processing (NLP) module, WALL-E could respond to basic voice commands like "Hello," "What are you feeling?" or "Look left." This enhancement would significantly improve WALL-E's interactivity by allowing users to communicate naturally, thus reducing barriers for those who may struggle with operating a mobile application.
  </p>
  <h3>4.3 Mobility and Autonomous Behavior</h3>
  <p>
    Currently, WALL-E is limited to stationary movements of its head and facial features. Adding mobility by equipping WALL-E with wheels or a crawler mechanism would enable it to follow users around, making it more akin to a robotic pet. Autonomous behavior could also be programmed—such as approaching users who appear to be sad or retreating when someone seems agitated. This mobility feature would allow WALL-E to act independently, enhancing the feeling of companionship.
  </p>
  <h3>4.4 Machine Learning for Emotional Adaptation</h3>
  <p>
    WALL-E could become more sophisticated by incorporating a machine learning model that allows it to adapt its emotional responses over time. A reinforcement learning approach could be used, wherein WALL-E learns what emotional responses are appropriate based on the feedback it receives. For instance, if a particular expression consistently results in positive user reactions, WALL-E could learn to use it more frequently. Such adaptability would move WALL-E from being a pre-programmed device to an intelligent, evolving robot capable of learning from its environment.
  </p>
  <h3>4.5 Integration with IoT Devices</h3>
  <p>
    In a connected smart home environment, WALL-E could be integrated with Internet of Things (IoT) devices to create a more immersive user experience. For example, WALL-E could detect when a user is stressed and dim the lights or play calming music through connected devices. This integration would make WALL-E more than just an emotional companion; it could become a central figure in a smart, responsive home designed around user well-being.
  </p>
</section>

<section id="conclusion">
  <h2>Conclusion</h2>
  <p>
    The development of WALL-E represents a significant effort in merging emotional expressiveness with robotics, emphasizing how technology can cater to the emotional needs of users. By using a combination of Arduino programming, sensor technology, servo-driven expressions, and mobile application interaction, WALL-E goes beyond traditional utility robots to offer emotional engagement, which is often lacking in current consumer robotics.
  </p>
  <p>
    The applications of WALL-E are vast, ranging from helping individuals with emotional expression challenges to providing companionship to the elderly and enhancing learning environments for children. Through non-verbal communication, WALL-E has the potential to reduce social isolation, improve emotional intelligence, and contribute positively to the quality of life of its users.
  </p>
  <p>
    While WALL-E’s current capabilities are impressive, future developments hold the promise of creating even deeper emotional bonds between robots and users. The incorporation of features like facial recognition, voice interaction, and machine learning can make WALL-E an adaptive and intelligent companion. These enhancements will allow WALL-E to evolve and respond dynamically to its environment, making it an even more effective emotional support tool.
  </p>
  <p>
    Ultimately, WALL-E serves as a prototype that demonstrates the value of affective robotics. It bridges the gap between emotional well-being and technological advancement, offering a glimpse of how robotics can enrich our lives emotionally. As the field of human-robot interaction continues to grow, projects like WALL-E will play a pivotal role in shaping how we integrate emotionally responsive robots into our daily routines.
  </p>
</section>

<section id="appendices">
  <h2>Appendices</h2>

  <h3>6.1 Code Overview</h3>
  <p>
    The code that drives WALL-E is written in C++, using the Arduino IDE. The code integrates multiple libraries to handle the LCD, LED matrix, servos, and ultrasonic sensors, making WALL-E’s reactions to human interaction seamless and emotionally expressive.
  </p>
  <h4>Libraries Used:</h4>
  <ul>
    <li><strong>LiquidCrystal_I2C.h</strong>: For controlling the 16x2 LCD screen used to display WALL-E’s emotional states.</li>
    <li><strong>LedControl.h</strong>: For managing the 8x8 LED matrices that form WALL-E’s eyes, allowing for expressive visual feedback.</li>
    <li><strong>Servo.h</strong>: For controlling the four servo motors—two for the eyebrows and two for head tilting and panning.</li>
    <li><strong>NeoSWSerial.h</strong>: For communication through the HC-05 Bluetooth module, which allows remote control via a mobile app.</li>
  </ul>
  <h4>Code Explanation:</h4>
  <ul>
    <li><strong>Setup and Initialization</strong>: The <code>setup()</code> function initializes the LCD screen, LED matrices, servos, and communication protocols.</li>
    <li><strong>Loop and Logic Control</strong>: The <code>loop()</code> function handles the continuous behavior of WALL-E, such as distance measurement and Bluetooth integration.</li>
  </ul>

  c++
//pre-existing libraries
#include <LiquidCrystal_I2C.h>
#include <LedControl.h>
#include <Servo.h>
#include <NeoSWSerial.h>
// Pins for LED matrix connected to Arduino
int DIN = 11;
int CS = 9;
int CLK = 10;
int DIN_2 = 6;
int CS_2 = 8;
int CLK_2 = 7;

// Create instances for LCD and LED matrix
LiquidCrystal_I2C lcd(0x27, 16, 2);
LedControl ledmatrix = LedControl(DIN, CLK, CS);
LedControl ledmatrix_2 = LedControl(DIN_2, CLK_2, CS_2);

//create instances for bluetooth pins
NeoSWSerial bluetooth(A1, A0);


// Create instances for the Servos
Servo pan;
Servo tilt;
Servo leftBrow;
Servo rightBrow;

// Pins for the ultrasonic sensor
const int trigPin = 13;
const int echoPin = 12;

// Variable to measure distance
float duration, distance;

// bluetooth state variables 
unsigned char state = 'N';
char recVbuffer[32];
unsigned recVindex =0;

// Bitmap patterns for emotions
byte neutral_bmp[8] = {B00000000, B00111100, B01000010, B01011010, B01011010, B01000010, B00111100, B00000000};
byte happyL_bmp[8] = {B00000000, B00011100, B00100100, B01011100, B01011100, B00100100, B00011100, B00000000};
byte happyR_bmp[8] = {B00000000, B00111000, B00100100, B00111010, B00111010, B00100100, B00111000, B00000000};
byte loveL_bmp[8] = {B00011000, B00100100, B01000010, B10000001, B10000001, B10011001, B01100110, B00000000};
byte loveR_bmp[8] = {B00011000, B00100100, B01000010, B10000001, B10000001, B10011001, B01100110, B00000000};
byte sad_bmp[8] = {B10000001, B01000010, B00100100, B00011000, B00011000, B00100100, B01000010, B10000001};
byte surprisedL_bmp[8] = {B00000000, B01111110, B01000010, B01000010, B01000010, B01000010, B01111110, B00000000};
byte surprisedR_bmp[8] = {B00000000, B01111110, B01000010, B01000010, B01000010, B01000010, B01111110, B00000000};

// Function to display pattern on LED matrix
void displayPattern(byte patternL[], byte patternR[]) {
  for (int i = 0; i < 8; i++) {
    ledmatrix.setColumn(0, i, patternL[i]);
    ledmatrix_2.setColumn(0, i, patternR[i]);
  }
}

// Function to write emotion on LCD
void displayEmotion(String emotion) {
  lcd.clear();
  lcd.print(emotion);
}

// Function to move servos
void moveServos(int left, int right, int panIn, int tiltIn) {
  leftBrow.write(left);
  rightBrow.write(right);
  pan.write(panIn);
  tilt.write(tiltIn);
}

// Function to measure distance using ultrasonic sensor
float measureDistance() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  return (duration * 0.0343) / 2;
}

//variables for led lights to make code quicker
unsigned long lastBlinkTime = 0;
bool isDisplayOn = true;


void setup() {
  // Debugging
  Serial.begin(9600);
  bluetooth.begin(9600);

  // Set up LCD
  lcd.init();
  lcd.backlight();

  // Set up LED matrices
  ledmatrix.shutdown(0, false);
  ledmatrix.setIntensity(0, 1);
  ledmatrix.clearDisplay(0);

  ledmatrix_2.shutdown(0, false);
  ledmatrix_2.setIntensity(0, 1);
  ledmatrix_2.clearDisplay(0);

  // Initialize columns with letters
  displayPattern(neutral_bmp, neutral_bmp);  // Initial neutral pattern
  displayEmotion("Neutral");  // Initial neutral emotion

  // Define input/outputs
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);

  // Attach servos
  pan.attach(5);
  tilt.attach(4);
  leftBrow.attach(2);
  rightBrow.attach(3);

  // Set initial positions
  moveServos(60, 90, 130, 90);

  
}

void loop() {
//logic to display text on LCD screen
if(state == 255){
  if(bluetooth.available() > 0){
    char recieved = bluetooth.read();
    if(recieved == 0){
      state = 0;
      recVbuffer[recVindex] =0;
      displayEmotion(recVbuffer);
      Serial.println(recVbuffer);
      delay(3000);
    }
    if(recVindex < 33){
      recVbuffer[recVindex] = recieved;
      recVindex += 1;
      if(recVindex == 16){
        
        recVindex += 1;
      }

    }
  }
  return;
}
  distance = measureDistance();
//initalize bluetooth
if (bluetooth.available() > 0) {
  state = bluetooth.read();
  Serial.println((unsigned)state);

}

if(state ==255){
  recVindex =0;
  return;

}

  // Priority handling: Motion detection takes precedence
  if (distance <= 10 && distance > 0) {
    moveServos(60, 120, 130, 90);
    displayPattern(sad_bmp, sad_bmp);
    displayEmotion("Please back up!");
    for (int i = 90; i > 45; i--) {
      delay(10);
      tilt.write(i);
    }
    for (int j = 45; j < 135; j++) {
      delay(10);
      tilt.write(j);
    }
  } else if (distance <= 30 && distance > 10) {
    tilt.write(90);
    displayPattern(happyL_bmp, happyR_bmp);
    displayEmotion("I am so happy");
    leftBrow.write(90);
    rightBrow.write(90);
    for (int i = 150; i > 110; i--) {
      delay(10);
      pan.write(i);
    }
    for (int j = 110; j < 150; j++) {
      delay(10);
      pan.write(j);
    }
  } else if (distance <= 50 && distance > 30) {
    displayEmotion("I love you");
    moveServos(90, 90, 130, 90);
    displayPattern(loveL_bmp, loveR_bmp);
    delay(500);  // On for 500ms
    ledmatrix.clearDisplay(0);  // Turn off left matrix
    ledmatrix_2.clearDisplay(0);  // Turn off right matrix
    delay(500);  // Off for 500ms
  } else {
    //switch cases to handle buttons pressing in app
       switch (state) {
  case 'A':
    displayPattern(sad_bmp, sad_bmp);
    displayEmotion("I am Angry!");
     moveServos(60, 120, 130, 90);
    for (int i = 90; i > 45; i--) {
      delay(10);
      tilt.write(i);
    }
    for (int j = 45; j < 135; j++) {
      delay(10);
      tilt.write(j);
    }
    break;

  case 'H':
    displayPattern(happyL_bmp, happyR_bmp);
    displayEmotion("I am Happy!");
    moveServos(120, 60, 130, 90);
    leftBrow.write(90);
    rightBrow.write(90);
    for (int i = 150; i > 110; i--) {
      delay(10);
      pan.write(i);
    }
    for (int j = 110; j < 150; j++) {
      delay(10);
      pan.write(j);
    }
    break;

  case 'N':
    displayPattern(neutral_bmp, neutral_bmp);
    displayEmotion("Hello!");
    moveServos(120, 60, 130, 90);
    break;

  case 'B':
    displayEmotion("Love!");
    moveServos(120, 60, 130, 90);
    if (millis() - lastBlinkTime >= 500) {
      lastBlinkTime = millis();
      if (isDisplayOn) {
        ledmatrix.clearDisplay(0);
        ledmatrix_2.clearDisplay(0);
      } else {
        displayPattern(loveL_bmp, loveR_bmp);
      }
      isDisplayOn = !isDisplayOn;
    }
    break;

  case 'L':
    displayEmotion("Looking Left");
    if (tilt.read() > 20) {
      tilt.write(tilt.read() - 3);
      delay(1);
    }
    break;

  case 'R':
    displayEmotion("Looking Right");
    if (tilt.read() < 160) {
      tilt.write(tilt.read() + 3);
     delay(1);
    }
    break;

  case 'U':
    displayEmotion("Looking Up");
    if (pan.read() > 75) {
      pan.write(pan.read() - 3);
      delay(1);
    }
    break;

  case 'D':
    displayEmotion("Looking Down");
    if (pan.read() < 160) {
      pan.write(pan.read() + 3);
      delay(1);
    }
    break;

  case 'Z':
    // Do nothing, keep the current position
    break;

  default:
    displayPattern(neutral_bmp, neutral_bmp);
    displayEmotion("Hello!");
    moveServos(120, 60, 130, 90);  // Eyebrows up, slight head tilt up
    break;
}
}
}

</section>

# Bill of Materials


| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| HC-05 Bluetooth Module | Connect bluetooth with phone allowing servos to move | $10.39 | <a href="https://www.amazon.com/HiLetgo-Wireless-Bluetooth-Transceiver-Arduino/dp/B071YJG8DR"> Link </a> |
| Microservos(2x) | Controlling eyebrows | $7 | <a href="https://www.amazon.com/Diitao-Geared-Helicopter-Airplane-Controls/dp/B0B885YW36/ref=asc_df_B0B885YW36/?tag=hyprod-20&linkCode=df0&hvadid=692875362841&hvpos=&hvnetw=g&hvrand=5259485647923795901&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9032183&hvtargid=pla-2281435178098&mcid=21a1d1f34f8237598b1b6c5e3c0c80b7&hvocijid=5259485647923795901-B0B885YW36-&hvexpln=73&gad_source=1&th=1"> Link </a> |
| Servos(2x) MG995 | Controlling the head and neck | $10.39 | <a href="https://www.amazon.com/180%C2%B0Metal-Waterproof-Airplane-Helicopter-Mechanical/dp/B09JWK2GB3/ref=asc_df_B09JWK2GB3/?tag=hyprod-20&linkCode=df0&hvadid=692875362841&hvpos=&hvnetw=g&hvrand=2101373794074905324&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9032183&hvtargid=pla-2281435178138&mcid=c8149b27222b305fba9ddb599ece2ec9&hvocijid=2101373794074905324-B09JWK2GB3-&hvexpln=73&gad_source=1&th=1"> Link </a> |
| Ultrasonic sensor HC-SR04| Detect motion using sound waves | $6.40 |<a href=" <https://www.amazon.com/HC-SR04-Ultrasonic-Distance-Measuring-MEGA2560/dp/B088BT8CDW/ref=asc_df_B088BT8CDW/?tag=hyprod-20&linkCode=df0&hvadid=692875362841&hvpos=&hvnetw=g&hvrand=7609019556708301176&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9032183&hvtargid=pla-2281435177658&psc=1&mcid=a96bc6df1ca933c4baf6476b09ca6103&hvocijid=7609019556708301176-B088BT8CDW-&hvexpln=73&gad_source=1"> Link </a> |
|8 by 8 LED matrix | Controlling eye emotions | $4.88 | <a href="https://www.walmart.com/ip/clearance-LED-Matrix-Control-Module-8x8-64-Bit-Panel-SPI-Interface-DC5V-Single-Board-Computers/6434003609?wmlspartner=wlpa&selectedSellerId=102484000&adid=222222222276434003609_102484000_167031288608_21207942474&wl0=&wl1=g&wl2=c&wl3=697286723488&wl4=pla-2298622009165&wl5=9032183&wl6=&wl7=&wl8=&wl9=pla&wl10=5386222348&wl11=online&wl12=6434003609_102484000&veh=sem&gad_source=1&gclid=CjwKCAjw1920BhA3EiwAJT3lSRxWi1_gpi8FM95eynM6ggweOeLFIsdYQRsJ3R6aQMW4fitOrpKxqRoCOQEQAvD_BwE"> Link </a> |
| LCD Screen | displaying message| $9.99 | <a href="https://www.amazon.com/SunFounder-Serial-Module-Display-Arduino/dp/B019K5X53O/ref=asc_df_B019K5X53O/?tag=hyprod-20&linkCode=df0&hvadid=692875362841&hvpos=&hvnetw=g&hvrand=17963529301046934762&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9032183&hvtargid=pla-2281435178338&mcid=d8869fd4bb8c3e78a3b0ed4cc311f13b&hvocijid=17963529301046934762-B019K5X53O-&hvexpln=73&gad_source=1&th=1"> Link </a> |
|Battery pack| Power Servos | $5.98 | <a href="https://www.amazon.com/LAMPVPATH-Battery-Holder-Leads-Wires/dp/B07T7MTRZX/ref=asc_df_B07T7MTRZX/?tag=hyprod-20&linkCode=df0&hvadid=692875362841&hvpos=&hvnetw=g&hvrand=7413704186770057061&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9032183&hvtargid=pla-2281435178858&psc=1&mcid=bc8a49e084dd3e049c6d15e853396eaa&hvocijid=7413704186770057061-B07T7MTRZX-&hvexpln=73&gad_source=1"> Link </a> |
|Arduino UNO | Code processor | $27.60| <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/ref=asc_df_B008GRTSV6/?tag=hyprod-20&linkCode=df0&hvadid=692875362841&hvpos=&hvnetw=g&hvrand=17095102518390285633&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9032183&hvtargid=pla-2281435179978&mcid=8d4415853f19330eb6cb8c1e7f18a8ed&hvocijid=17095102518390285633-B008GRTSV6-&hvexpln=73&gad_source=1&th=1"> Link </a> |
| Mini breadboard| helps providing processing power to servos| $6.75 | <a href="https://www.amazon.com/BB400-Solderless-Plug-BreadBoard-tie-points/dp/B0040Z1ERO/ref=asc_df_B0040Z1ERO/?tag=hyprod-20&linkCode=df0&hvadid=692875362841&hvpos=&hvnetw=g&hvrand=10172484802440772633&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9032183&hvtargid=pla-2281435177658&psc=1&mcid=df8a82d513d937b38ac19209b20d38be&hvocijid=10172484802440772633-B0040Z1ERO-&hvexpln=73&gad_source=1">Link </a> |
|Various M2 && M3 screws |assembly toolbox |$4.99 |<a href="https://www.amazon.com/DYWISHKEY-Pieces-Screws-Washers-Assortment/dp/B0CS9XVPLV/ref=sr_1_5?dib=eyJ2IjoiMSJ9.dh4QCEmZvciH5SBORhOCf75bMouvuVRAsfpzKgwH7vL3qE9hVvCkxHXIMEjY3AClbjCj1nowLTLXTWy9HpeeP_tURjiAhK6mKqwFIo94IAfClGjb6uS9TiMjzUswBqIJIi-8yiN-r17e9sW8e3-ywAt1h08lW7GXovk9ds6Vhvh11-V1cUFeQ_gNbs6nwPZtDqS5q0gNuZNU8O0UmgbdjWT7UU9cZF7B8GTORgzF8qw.WdawQ8PMaipfzxLESkhHX3kY3M3VV__lwt6X6uq1M5Y&dib_tag=se&hvadid=409999246310&hvdev=c&hvlocphy=9032183&hvnetw=g&hvqmt=b&hvrand=2835700877264352192&hvtargid=kwd-933490677&hydadcr=26614_10407671&keywords=m3%2Bscrews&qid=1721257749&sr=8-5&th=1">Link </a> |
|various jumper cables|connecting all components together|$5.98|<a href=" https://www.amazon.com/Elegoo-EL-CP-004-Multicolored-Breadboard-arduino/dp/B01EV70C78/ref=asc_df_B01EV70C78/?tag=hyprod-20&linkCode=df0&hvadid=692875362841&hvpos=&hvnetw=g&hvrand=743854505051106635&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9032183&hvtargid=pla-2281435178578&mcid=6d8a7ca3c39a3ad4877ede949dc655a6&hvocijid=743854505051106635-B01EV70C78-&hvexpln=73&gad_source=1&th=1"> Link </a> |
|3D printed parts|Container of robo|


<div style="display: flex; align-items: center; justify-content: space-between;">
  <img src="download.gif" style="width: 100%; height: 70%;" alt="First Image">
</div>

