# R'Mailbox - UCR Spring 2020 Senior Design Project

![License](http://img.shields.io/github/license/mrthomaschin/CS179J-Team3)

<img src="https://user-images.githubusercontent.com/22509729/119739432-159cac00-be37-11eb-827e-dae3f5d5c7ae.png" width="400" /> <img src="https://user-images.githubusercontent.com/22509729/119739411-0ddd0780-be37-11eb-8a68-b3327f03c319.png" width="500" /> 
![team3](https://user-images.githubusercontent.com/22509729/119741248-2b5fa080-be3a-11eb-9956-410119fca1cd.png)

*Note: This project was developed at the start of the COVID 19 pandemic when our university was closed down. As such, we had to take our pictures and demo videos in a living room. Sorry!*

<br>

## Demo Video

[Link](https://youtube.com)

<br>

## Project Overview

R'mailbox is an IoT mailbox created by Thomas Chin, Noah Jimenez, Jacob Halvorson, Michael De Sousa, and Christian Grayson in the spring of 2020. 

It is designed to be a "smart", secure container that can be used to send/receive mail and packages. The R'Mailbox uses IR sensors and a load cell to detect when mail has been placed inside of the main compartment. Once mail has been detected inside the compartment and the compartment door is closed, a servo automatically locks the door. From here, an SMS notification and email are automatically sent to the owner of the mailbox using [Twilio](https://www.twilio.com/). When the owner wants to open the R'mailbox and retrieve the mail inside, they can unlock the door with 3 unique authentication methods.

First, the owner can press the "Request to Open" button on the R'mailbox. This will send an SMS request to the owner's phone. They can reply with "Yes" to remotely unlock the door, or "No" to keep it locked. Second, the owner can open the door using facial recognition. The R'mailbox has a built in camera and can register multiple different faces in its memory. When an authorized face is detected, the compartment door will automatically unlock. Finally, the owner can opt to open the door using a built in fingerprint scanner. The fingerprint scanner can register multiple different fingerprints and will unlock the door when an authorized fingerprint is detected, similar to the facial recognition.

When the owner wants to send something, they can press press the "Outgoing Mail" button on the R'mailbox. They can then simply place their mail inside of the compartment and close the door. A servo will automatically lock the door to keep the outgoing mail secure. A second servo will automatically raise a mail flag on the side of the R'mailbox, to alert the postal worker when they arrive. The postal worker can use the previously mentioned "Request to Open" button to allow the R'mailbox owner to remotely open the door. An SMS notification and email are sent to the owner once the outgoing mail has been removed from the compartment. 

The R'mailbox also has Amazon Alexa integration. At any point, the owner can use an Echo Dot or the Alexa app to ask Alexa about the status of the R'mailbox. They can ask if any mail has been delivered to the container, or if outgoing mail has been picked up. In either case, Alexa will ping the R'mailbox (using a Flask server) to figure out the status of the package sensors and answer the owner's question.

A simple diagram of the system interfaces can be seen below: 

![rmailbox_diagram](https://user-images.githubusercontent.com/22509729/119742026-c1e09180-be3b-11eb-9d0f-ecfbbb50c89b.png)

<br>

## Technologies Used

Hardware:
- Raspberry Pi 3B+
- Raspberry Pi Zero W
- Atmega1284 Microcontroller 
- SG90 Servo Motor
- AS608 Fingerprint Scanner
- PiCamera
- E18-D80NK IR Sensor
- HX711 Load Cell + Amplifier

Programming Languages:
- Python
- C

Additional Tools:
- Flask
- TravisCI
- Amazon Alexa Skills
- SPI communication (between Raspberry Pi and Atmega1284)

## Additional Documentation

A detailed report of our project can be found [here](https://drive.google.com/file/d/1L6dqv_ulrA3YTHF-tuNcpjMuraq7k0kp/view?usp=sharing). It includes additional diagrams of our subsystems, a full Bill of Materials, a breakdown of our testing methodology, and much more.
