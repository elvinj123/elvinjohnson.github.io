---
layout: page
title: Deepfakes
description: Detecting Deepfakes videos using Deep Learning 
img: /assets/img/Deepfake Cover.jpg
importance: 1
category: Academic and Personal Projects
---

Deepfakes are videos in which a persons face is swapped with that of another person or another persons lip movements are transfered to that of another using various techniques. Using this, a person can be made to say anything, provided a few pictures of the person targeted are available, thus, allowing a person to defame the targeted individual. Deepfakes videos can be particularly dangerous when it comes to politics. The following is an illustration of how lip sync and faceswap can be used to create Deep fakes. 

<div class="row justify-content-sm-center" >
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/putin deepfake.gif' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
            FIGURE 1: LIP SYNC DEEPFAKE
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/nicolas cage deepfake.gif' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
            FIGURE 2: FACESWAP DEEPFAKE
        </div>
    </div>
</div>
The following is a deepfake video of former president Barack Obama. In this video, he was made to say dishonorable things by means of transfering the lip movements of another person onto his. 
<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        <!-- <video width="320" height="240" autoplay muted> -->
        <center>
            <video  width="500" height="350" controls>
                <source class="img-fluid rounded z-depth-1" src="{{ '/assets/img/obama actual fake.mp4' | relative_url }}" type="video/mp4">
            </video> 
        </center>
    </div>
</div>
<div class="caption">
    VIDEO 1: OBAMA DEEPFAKE
</div>
Before being able to work on detection, we had to understand Generative Advarsarial Networks (GANS), which was one the major recent breakthroughs in deep learning that was misused to create deepfake videos. The following grid of images consists of human faces that never existed, which we generated using GANS. The NVIDIA DGX-1 AI SUPERCOMPUTER was used for this.  
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img height="500" class="img-fluid rounded z-depth-1" src="{{ '/assets/img/gans1.JPG' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
        FIGURE 3: GRID OF GENERATED FACES
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img height="200" class="img-fluid rounded z-depth-1" src="{{ '/assets/img/gans2.JPG' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
        FIGURE 4: GRID OF GENERATED FACES
        </div>
    </div>

</div>

My main task was to preprocess the data, get it ready and to build the detection model. I also took lead in preparing a <a href="https://ieeexplore.ieee.org/abstract/document/9225400">research paper </a> for the same and presented it at the 11th International Conference on Computing, Communication and Networking Technologies (ICCCNT) 2020, held at Indian Institute of Technology, Kharagpur.

<h5><b>Dataset Creation</b></h5>
 Considering the fact that deepfakes were being created via many sophisticated methods, it was important for the model to be able to identify and to be able to generalize to all of these. Hence, for dataset creation we processed, cleaned and mixed about a <b>million</b> frames from deep fake datasets by Facebook, FaceForensics, Google to use as the training dataset. Faces had to be extracted from each frame of a video. DLIB (deep learning based face detection) and MTCNN (deep learning based face detection) were used for this. Due to the sheer size of the data, processing the entire dataset took more than a week on the NVIDIA DGX-1 Supercomputer. 

<h5><b>Training Procedure</b></h5>
To foster better performance and to reduce training time, transfer learning was used. In transfer learning, the data in the source and target domain are not required to be identically distributed i.e the model in target domain need not be trained from scratch, which can significantly reduce the demand of training data and training time. Also, transfer learning also implies that the knowledge gained in the source domain would be transferred to the target domain, thus, helping the model achieve better accuracy in the target domain. Hence, transfer learning was used.

Using the master dataset created as above, a number of different custom CNN based models were created and trained by using different base models. Base models like those of the InceptionV3, ResNet50, etc., were used. As part of employing transfer learning, the initial starting weights were those obtained by training these models on the ImageNet dataset (A dataset containing images several images belonging to 1000 categories). Several custom layers were then added to these base models and their weights were randomly initialized. Training was performed on the NVIDIA DGX-1 AI SUPERCOMPUTER, that hosted 8 Tesla V100 GPU's, in the lab I was working in. A generalized model was thus created. This project also resulted in a <a href="publication">publication</a>. Figure 5 and Figure 6 show the DGX-1 setup.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img height="500" class="img-fluid rounded z-depth-1" src="{{ '/assets/img/dgx1_adobespark(1).jpg' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
        FIGURE 5: THE NVIDIA DGX-1
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img height="200" class="img-fluid rounded z-depth-1" src="{{ '/assets/img/dgx2_adobespark.jpg' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
        FIGURE 6: OVERNIGHT TRAINING ON THE DGX-1
        </div>
    </div>

</div>
 The following are deepfake videos tested on the final model. As seen in the top left corner, the model indicates the probability of each frame of the video being fake, the prediction is correct here.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <video  width="500" height="350" controls>
                <source class="img-fluid rounded z-depth-1" src="{{ '/assets/img/Obama_Final.mp4' | relative_url }}" type="video/mp4">
            </video> 
        </center>
    </div>
</div>
<div class="caption">
    VIDEO 2: OBAMA DEEPFAKE DETECTED BY THE MODEL
</div>


Following is a deep fake video of Jeff Bezos and Elon Musk. Their faces have been morphed/swapped into characters from the clip for the movie Star Trek. The model was correctly able to detect this as well.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <video  width="500" height="350" controls>
                <source class="img-fluid rounded z-depth-1" src="{{ '/assets/img/Musk bezos.mp4' | relative_url }}" type="video/mp4">
                <!-- <source class="img-fluid rounded z-depth-1" src="{{ '/assets/img/Jeremy_Boris_Final.mp4' | relative_url }}" type="video/mp4"> -->
            </video> 
        </center>
    </div>
</div>
<div class="caption">
    VIDEO 2: MUSK-BEZOS DETECTED BY THE MODEL
</div>

<h5><b>Key takeaways</b></h5>
1. I learnt a lot about <b>handling data in this project due to the sheer magnitude of the data</b> we had to use. A lot of time had to be devoted to this. Initially only 2 datasets were used, however later, to improve accuracy, newer ones had to incorporated. Since, processing the data would take more than a week (the supercomputer would remain onn for an entire week), debugging and saving current data had to be taken care of. For eg, twice during the processing, the machine had shut down due to power outages and writing code to resume from where it was cutoff was critical.
2. Detecting deepfakes is a critical task. Deepfakes can create political unrest and spread misinformation. <b>For such critical applications, it is better to train multiple models</b> (if accuracy is around 85%-90%). In this way, mulitple models could vote on an output and avoid false negatives and false positives.
3. <b>Detailed research of current methods is important.</b> Deep fakes are ever evolving and newer and newer methods for generating them are being invented day after day. Hence, it is important to build machine learning models with this in mind.
4. <b>The more the data, better is the reliability of models.</b> In this project, 3 different datasets were mixed, thus, helping in the creation of a reliable model.
5. <b>Documenting progress is very important.</b> It always helps keep a tab on what had not worked and not worked earlier during the project. This helps save valuable time later on.


