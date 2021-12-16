---
layout: page
title: Detection of skin cancer using ML
description: A machine learning based approach for detecting and classifier skin cancer using images   
img: /assets/img/skin classifier cover.JPG
# redirect: https://unsplash.com
importance: 4
category: Internship
---
I completed the following project while interning at my undergraduate institute over the summer. The main objective of this project was to perform detection and classification of skin cancer using images. The approach followed was to construct deep learning based classifiers that would provide a two-fold utility whereby it would enable:
1. Identification of tumour (benign or malignant).
2. Classification of tumour into seven distinct categories (if malignant). 

Two classifiers were created, one to classify skin lesions as benign/malignant and another to classify it into one of the seven types of skin lesions, if found to be malignant. Figure 1 illustrates how a test will be carried out after taking a picture of the skin lesion and passing it through the two stages of the model.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/skin classifier cover.JPG' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>
</div>
<div class="caption">
    FIGURE 1: DETECTION PROCEDURE
</div>

The dataset used to train the models consisted of dermoscopic images from HAM1000 Dataset (By International Skin Imaging Collaboration). The main responsibility that I had handled was to build and train the models. Back then, I had learnt that architectures like the InceptionV3, Resnet50, VGG16 etc, were state of the art image classification models, after having experimented with basic models. I used the above mentioned CNN models as base models and added custom layers to these models, to create a complete model. 

Also, after much research I found that using transfer learning was the most appropriate approach to follow, since they would help the model train faster and perform better. For this, the model was initialized using the pretrained weights obtained by trianing the model on the Imagenet (a huge data set of multiclass images) data set. Various models were then trained over a period of several days and the model that would classify the lesion as benign or malignant achieved an accuracy of 89% and the model that classified the image into one of the seven types showed and accuracy of 85%. I believe the accuracy could have been improved further, however, due to lack of sufficient compute power at that point, this was not possible. 

 Figure 2 gives a pictures of the training and testing pipleline.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/detection of skin cancer process 1.jpg' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>
</div>
<div class="caption">
    FIGURE 2: TRAINING/TESTING PIPELINE
</div>



<h5><b>Final Takeaways</b></h5>
1. This was the first project I had done in deep learning. From this project, I realized how powerful deep learning/machine learning and how it could impact human lives for the good.
2. <b>Using Transfer learning is a great help</b> when it comes to a classification problem. It not only improves model performance, but also helps in training a model faster.
3. In deep learning, there are no fixed set of rules that one could follow w.r.t the size/depth of the model, the number of neurons etc. Many factors, like the right architecture to be used can be understood only through trial and error. For eg, while adding custom layers to the model, I realized that some architectures perform well, while others do not.
4. When it comes to machine learning for medical/life critical applications, accuracy is of utmost importance. This was a challenge I had faced. An accuracy above 95% is a must, I feel for such applications. I realized that in such cases, multiple models could be trained and then vote for passing the final verdict in such cases. This would help reduce false negatives and false positives.


