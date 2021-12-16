---
layout: page
title: Accident Detection and Alert system
description: An smart accident alert system for saving lives
img: /assets/img/accident detection and alert cover.JPG
importance: 8
category: Academic and Personal Projects
---

One of the major cause of the accidents is the high speeding of vehicles. In most of the cases, the victims die due to lack of timely medical assistance which is a major setback despite of the availability of post-accident emergency facilities. The loss of lives could be minimized if the accident information is provided immediately to the nearby hospitals thereby allowing the victim to receive the medical aid. This project aims at resolving the aforementioned issue by implementing an accident detection and alert system using Arduino, GPS and GSM modules and vibration disk sensor. The approach would be that the vibration sensor would sense the collision and produce a certain voltage value which would be read and digitized by the ATMEL microcontroller on the Arduino board. When value of the vibration sensor exceeds a particular threshold an alert message would be sent to the pre-coded numbers by GSM module along with the exact accident location. The accident location would be specified as latitude and longitude retrieved from satellite via GPS module. Figure 1 is a snapshot of the hardware setup.

<div class="row justify-content-sm-center" >
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/accident_system_setup.jpg' | relative_url }}" alt="" title="example image"/>
            <div class="caption">
                FIGURE 1: FLOWCHART OF THE ALGORITHM
            </div>
        </center>
    </div>
</div>

<h5><b>Working</b></h5>
1.The vibration sensor senses the collision and produces a certain voltage value which would be read by UNO. 
2.When the value provided by the vibration sensor exceeds a particular threshold the UNO reads it as digital high and sends an alert message to the pre-coded numbers by GSM module along with the exact accident location.
3.The accident location will be specified as latitude and longitude read by the UNO from the GPS module. Also, the location in the sms can be accessed on Google Maps. Figure 2 shows the flowchart of the algorithm.



<div class="row justify-content-sm-center" >
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/flowchart accident detection.JPG' | relative_url }}" alt="" title="example image"/>
            <div class="caption">
                FIGURE 2: FLOWCHART OF THE ALGORITHM
            </div>
        </center>
    </div>
</div>
