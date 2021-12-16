---
layout: page
title: Signature Extraction
description: A webapp for extracting signatures from documents using ML
img: /assets/img/signature cover.jpg
importance: 1
category: Internship
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/protiviti-logo.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
I completed this project while interning with <a href="https://www.protiviti.com/IN-en">Protiviti</a>. Here, I developed an end-to-end solution for signature extraction where a machine learning model was trained to identify, extract signatures from an input document. Finally a signature detection webapp was created for deploying the trained model. Below is the final working demo of the same.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        <!-- <video width="320" height="240" autoplay muted> -->
        <center>
            <video  width="500" height="350" controls>
                <source class="img-fluid rounded z-depth-1" src="{{ '/assets/img/signature demo.mp4' | relative_url }}" type="video/mp4">
            </video> 
        </center>
    </div>
</div>
<div class="caption">
    VIDEO 1: SIGNATURE EXTRACTION APP DEMO
</div>

Since I was assigned to do this project fully, I had to perform most of the tasks whilst keeping my manager updated regularly. The client needed a system that would allow for the automatic detection and extraction of signatures from customer documents, in a quick and efficient manner. The approach I followed was to train a deep learning based machine learning model to <b>detect</b> and <b>extract</b> signatures, which could be deployed later to an app, with the model running in the backend. Following were the steps I undertook.

<h5><b>Data Collection and Preparation</b></h5>
In this stage, to train the models, documents with annotations(with bounding boxes around signatures) had to be acquired. The dataset I used was an open source <a href="http://tc11.cvc.uab.es/datasets/Tobacco800_1"> dataset</a>. As for the models, the Tensorflow API provides a lot of state of the art model architectures that could be used for training models for general object detection. To train these models, I had to convert the data to to tf.record format. 

<h5><b>Training and Testing</b></h5>
Once the data was prepared, I had to train and configure a few of the models I had selected from the models available in the Tensorflow API. For training, I used the GPU's provided by Google Colab over the cloud, to help train the models much faster. During testing, once the signatures were detected in a test document, they had to be extracted using the coordinates of the bounding box drawn around them as in Figure 1. 

To tackle the problem of low training data, I performed data augmentation. Also, to surmount the issue of the model mistaking shabbily written handwritten text for signatures, I incorporated handwritten data in to the non-signature class.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/signature procedure.JPG' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>
</div>
<div class="caption">
    FIGURE 1: THE SIGNATURES ON THE RIGHT HAVE BEEN EXTRACTED FROM THE DOCUMENT ON THE LEFT
</div>

<h5><b>Creating a local Webapp</b></h5>
Once the training was complete, I created a local webapp where one could upload documents and have the signatures extracted from them by the trained model, with the model running in the background. The webapp could simply be run using a .bat Windows command file (a run icon), which would run a script locally and open the app in a browser. Figure 1 above shows the output of the test performed on a document. 


<h5><b>The Webapp</b></h5>
Following are a few screenshots of the webapp, (From the video posted above)

Step 1: Open the app by clicking the icon of the .bat file
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/page 1.JPG' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>
</div>
<div class="caption">
    FIGURE 2: THE LANDING PAGE
</div>

Step 2:  Click on browse, and upload the document from which signatures are to be extracted
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/page 2.JPG' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>
</div>
<div class="caption">
    FIGURE 3: THE UPLOADING AND PREVIEW PAGE
</div>
Step 3: Click on Detect signatures and get the extracted signatures which can be downloaded in the next page
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/page 3.JPG' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>
</div>
<div class="caption">
    FIGURE 4: DOWNLOAD THE EXTRACTED SIGNATURES
</div>

<h5><b>Final Takeaways</b></h5>
This was the first project I had completed, that involved creating a deployable version of an application that could run a machine learning model in the backend. It was also the first time that I had done such an extensive project in an industrial setting. The learnings were priceless. Following were the major takeaways:

1. <b>Preparing and getting the right data is very important</b>. It is worth spending a little extra time in researching and getting the right data, especially when it comes to machine learning models that need to be deployed, to avoid future hassles.  
2. <b>Accuracy is important for machine learning models that need to be deployed and the more the data, better would be the performance/accuracy</b>. I found it helpful to mix datasets, to help the models generalize better.
3. <b>Making use of open source resouces, whenever appropriate, helps save valuable time and effort</b>. 
4. <b>Constantly ask for feedback. It is sometimes easy to overlook improvements that could be made when you are doing a project on your own.</b> A fresh pair of eyes always help with getting good suggestions for imporvements.

<!-- ---
layout: page
title: Signature Extraction
description: A webapp for extracting signatures from documents using ML
img: /assets/img/signature cover.jpg
importance: 1
category: work
---

Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/1.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/3.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal it's glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/" target="_blank">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
``` -->
