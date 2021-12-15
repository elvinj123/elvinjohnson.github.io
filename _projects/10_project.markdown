---
layout: page
title: Voice Controlled Wheelchair
description: An IOT+Google assitant based voice controlled wheelchair
img: /assets/img/voice_controlled_cover.jpg
importance: 9
category: Academic and Personal Projects
---

<div class="row justify-content-sm-center" >
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/voice_controlled_cover.jpg' | relative_url }}" alt="" title="example image"/>
            <div class="caption">
                FIGURE 1: THE PROTOTYPE OF THE WHEELCHAIR
            </div>
        </center>
    </div>
</div> 

Physically challenged people like those suffering from paralysis/handicapped or being unable to walk find it very difficult to perform basic tasks. They are in continuous need of someone’s help to move around freely. This project aims at ameliorating the aforementioned problem of dependency on others by allowing the patients to traverse independently with the help of an intelligent wheelchair that would be empowered to understand pre-coded voice commands.  All the person who is sitting on the wheelchair must have is a smartphone which could be held in the hand or fixed onto the wheelchair. It would have Google assistant and the IFTT application pre-installed on it. The person can then create personalized commands for basic operations like moving forward, backward, left, right, stop. Certain values would be assigned for all the basic commands using the IFTT app and the Google Assistant. In our model, the command forward was assigned a value of ‘1’, backward a value of ‘0’, right a value of ‘2’, left a value of ‘3’, stop a value of ’4’. Additional commands for speed adjustment were also created. While programming the RaspberryPi board(The board controlling the motors) values corresponding to each command were taken into account.

The Pi board would respond to the voice commands by moving the wheelchair in specified direction as per the feed value fetched from an Adafruit_IO server using MQTT protocol over an internet connection. In this protocol, would be used wherein the Google Assistant acts as publisher, Adafruit IO as a broker and the Raspberry Pi as a subscriber. The patient would thus be able to easily control the motion of the wheelchair with minimum effort by using Google Assistant services for voice control. Also, an ultrasonic sensor was integrated into the wheelchair which would help to halt the wheelchair automatically upon detection of an unexpected obstacle within the specified safe limits.

<h5><b>Detailed Working of the MQTT protocol</b></h5>
For communication, we used Adafruit_IO services which is a free application that allows voice commands to be sent over the internet. Its working is based on the MQTT (Message Queuing Telemetry Transport) protocol.  MQTT depends on 4 basic concepts that are important:
1) Publish/Subscribe
2) Messages
3) Topics
4) Broker
The first concept is the publish and subscribe system. In a publish and subscribe system, a device can publish a message on a topic, or it can be subscribed to a particular topic to receive messages. Messages are the information that you want to exchange between your devices. Whether it’s a command or data.  Topics are the way you register interest for incoming messages or how you specify where you want to publish the message. The broker is primarily responsible for receiving all messages, filtering the messages, decide who is interested in them and then publishing the message to all subscribed clients.

In our case, we have used Google assistant which accepts voice commands. The IFTT app helps us assign values corresponding to each command. The voice commands are accepted and published onto the Adafruit_IO server. Thus, the Google assistant along with the IFTT application acts like the PUBLISHER in this case. For each voice command, a particular value is assigned beforehand as mentioned earlier. It publishes this specific value/integer onto the Adafruit Server corresponding to each command as and when the command is given via the assistant. Adafruit acts like the BROKER. 

Now, when the person gives a particular command, the wheelchair would respond accordingly. It would move just as a normal vehicle, but, with voice control. Also, the Ultrasonic sensor would stop the wheelchair in the instance where an unexpected object comes in front of it. It would override any command the user might give at that instant, thus, ensuring safety of the user.

