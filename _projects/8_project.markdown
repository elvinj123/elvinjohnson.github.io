---
layout: page
title: Smart Security System
description: A face detection based security system
 
img: /assets/img/smart securty cover new.jpg
# redirect: https://unsplash.com
importance: 7
category: Academic and Personal Projects
---

The main objective was to create a system that would enable a person to authenticate the person at the door of his or her own house remotely using a face detection system. A model was trained using Dlib(Deep Learning Library) that would be used to detect faces and learn the faces of the family members in a family. In case an unknown person is at the door, an image of the person would be clicked and sent to the owner via an automated email in order to receive authentication from the owner. Initially, I used opencv to detect identify faces, however, its lower accuracy was a major issue, so I had to move to DLIB(A deep Learning library) for detecting and recognizing the faces of the family members living in the owners house, which was much more accurate.  Once a persons picture was clicked, a Python script would be rune that would directly send the picture of the unknown person to the owner of the house. 



