---
layout: page
title: The Eyewriter
description: A wearable to enable paralysed individuals control a PC's cursor using their eyes
img: /assets/img/eyewriter cover.JPG
importance: 6
category: Academic and Personal Projects
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/SRA_logo4.jpg' | relative_url }}" alt="" title="example image"/>
            <!-- <div class="caption">
                FIGURE 1: THE VARIOUS COMPONENTS
            </div> -->
        </center>
    </div>
</div>

As a member of Society of Robotics(SRA) at my undergraduate institution, me and my teammates designed an Eyewriter, a system to control the cursor of a computer using eye movement to aid people who have ALS (paralysis of the limbs). The Objective was to design a wearable to control the cursor of a computer using eye movement to aid people with ALS disorder(paralysis) to control the cursor of a computer using their eyes. By tracking the movements of the pupil via a USB camera, using computer vision, we moved the cursor on a computer screen. (For eg if the eye moves to the left, the cursor moves proportionately to the left as well). Operations like double click, single click were also implemented by using long, short timed eye blinks. Opencv was used for image processing. The camera used was a PS4 camera and the light filter had to be removed carefully and replaced with another so that the image would be grayscale. 
<center>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/eyewriter 1.jpg' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
            FIGURE 1: THE VARIOUS COMPONENTS
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/eyewriter 2.jpg' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
            FIGURE 2: CLOSER VIEW OF THE CAMERA
        </div>
    </div>
</div>
</center>
<h3><b>Demo Video</b></h3>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <video  width="500" height="350" controls>
                <source class="img-fluid rounded z-depth-1" src="{{ '/assets/img/eyewriter demo.mp4' | relative_url }}" type="video/mp4">
            </video> 
        </center>
    </div>
</div>

