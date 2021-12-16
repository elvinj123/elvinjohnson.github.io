---
layout: page
title: Image Analytics in Retail
description: A Video/Image Analytics based approach towards providing a seamless Customer experience in the Retail sector
   
img: /assets/img/image analytics cover.JPG
# redirect: https://unsplash.com
importance: 2
category: Internship
---
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/protiviti-logo.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
I completed this project while interning with <a href="https://www.protiviti.com/IN-en">Protiviti</a>. Here, I collaborated with the data science team to identify relevant use cases for image analytics in the retail sector, worked on building solutions for the same and published a white paper on 'Image Analytics in Retail'. I had identified and worked on the 3 use cases as follows.

<h3><b>1. Finding the Degree of Similarity Between Images</b></h3>
The main objective over here is to find the percentage similarity between two inputted images.  Many a times, when we look for something in an online store, we click a picture of the product we want to buy and similar products show up. This reduces the time required for browsing and searching through an endless list of products! 

<!-- <h5><strong>Procedure</strong></h5> -->
<h5><b>Procedure</b></h5>
First, a deep learning CNN model is created and they are trained on images for a particular application, using training images in that domain. For example, they are trained on various supermarket product images. After training is complete, the two input images to be compared are read, resized and passed through through the model. Using the fact that the intermediate layers of the CNN learn to capture complex features from images in that particular domain, I extracted output vectors from one of these layers for both the input images and used these vectors for calculating the similarity. 

Because the CNN is trained for a particular application, the vectors would be similar for similar images and very different for different images. As an alternative for training, the model could be loaded with the weights obtained by training the models on the Imagenet dataset and then trained/fine tuned for any particular application if needed. The process is as shown in Figure 1.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 1 process.jpg' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>

</div>
<div class="caption">
FIGURE 1: PROCESS FLOW
</div>
<h5><b>Outputs</b></h5>
Figure 2 below gives some miscellaneous examples of pairs of objects whose Cosine and Pearson scores were calculated. It can be observed that for dissimilar objects, the scores are small and for similar images, the scores are larger.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 1 op1.JPG' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>

</div>
<div class="caption">
FIGURE 2: SOME COMPARISON PAIRS
</div>


<h3><b>2. Super Stores (Shelf/ Inventory Management)</b></h3>
Supermarket shelves have multiple products, many a times, customers pickup products and misplace them, while sometimes, the employees fail to restock the shelves despite the products being available in its inventory. Using machine learning and video analytics, these problems could be eliminated. Also, implementing the same in the inventory of a supermarket could help in keeping track of the stocks of each product available and that which is sold in the supermarket. 

The approach here is to train a object detection model on the items in the inventory of a supermarket, to enable it to recognize and track multiple objects in a supermarket shelf using a camera. These models could be later used as follows. The cameras would record live video feed, and by running CNN models on the cloud detection and classification could be carried out on every frame. Here, I have used images for testing, as in a real life scenario, a video would ultimately be converted to frames, and each frame would be treated as an image. The Tensorflow API by Google provides the architectures of many the detection and classification models that can be trained. Then, I trained various models on an open source dataset containing products in a particular supermarket store. Transfer learning was used as well.
<h5><b>Procedure</b></h5>
First, I obtained the dataset in the form of images along with labelled annotations (bounding boxes) of products in an image (50-70 instances of each product should be present across the pool of images). Then, using the annotations, I convert the data into tf.record format, which is a format in which it is inputted to the models in the Tensorflow API. Finally, the model was trained and while testing, bounding boxes are drawn around the objects along with the predicted labels. The process is shown in the Figure 3.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 2 process.jpg' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>

</div>
<div class="caption">
FIGURE 3: PROCESS FLOW
</div>
<h5><b>Outputs</b></h5>
The figure 4 shows a subset of the outputs obtained by testing performed using the Faster RCNN Resnet50 model that was trained on a few supermarket products like Head and Shoulders shampoo, Pantene shampoo, Rejoice Shampoo, Lays (chips) and Pickle.
<div class="row justify-content-sm-center" >
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 2 op1.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 2 op2.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 2 op3.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
FIGURE 4: SCANNED SHELF OUTPUTS
</div>

<h3><b>3. Multi- Object Detection (Automated Scanning)</b></h3>
The main objective here is to build a model that would be able to identify and classify multiple objects in an image. There are many scenarios wherein we need to perform multiple object detection in an image. For eg, at the checkout of a super market store, instead of having to scan each object one by one, many objects could be placed together, and with one single scan(clicking a picture), using object detection, billing could be made faster. This would help alleviate the problem of customers having to stand in long queues on busy days. 

The approach is to train a CNN on the items in the inventory of the store it is to be used for, to enable it to recognize objects using a camera, with help of object detection and classification. The Tensorflow API by Google provides the architectures of all the detection and classification models as discussed earlier.  
<h5><b>Procedure</b></h5>
First, I obtained the dataset in the form of images along with labelled annotations (bounding boxes) of products in an image (50-70 instances of each product should be present across the pool of images). Then, using the annotations, I convert the data into tf.record format, which is a format in which it is inputted to the models in the Tensorflow API. Finally, the model was trained and while testing, bounding boxes are drawn around the objects along with the predicted labels. The process is shown in Figure 5.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 3 process.jpg' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>

</div>
<div class="caption">
    FIGURE 5: PROCESS FLOW   
</div>
<h5><b>Outputs</b></h5>
Figure 6 is a subset of the outputs of images on which the Faster-RCNN-ResNet50 and RFCN-ResNet101 were tested.

<div class="row justify-content-sm-center" >
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 3 op1.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 3 op2.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/use case 3 op3.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    FIGURE 6: SAMPLE SETS OF DETECTED OBJECTS
</div>
Figure 7 gives the comparison of the test accuracy of the various models that I had trained
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/model_acc.JPG' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>

</div>
<div class="caption">
    FIGURE 7: TEST ACCURACY COMPARISON   
</div>

<h5><b>Final Takeaways</b></h5>
Following were some of the major takeaways, apart from others.

1. <b> Remaining abreast of the latest research and techiniques used in solving problems related to the domain of the project being done is very important.</b> This helps in solving the current problems in a more efficient manner. 
2. <b>Sometimes data won't be available in the manner it is desired. It needs to be given proper attention and worked upon.</b> For eg, I needed data of supermarket products, with the annotations. However, the annotations provided in the datasets were riddled with errors. Due to this, I had to annotate them manually. This took time, but I learnt that this is very important still.
3. <b>It is very important to document whatever is being done in a project from A-Z.</b> I realized this was important as I was asked to provide timely updates in PPT format, with meticulous attention to details. 
4. <b>While doing a project, there could be various approaches in which a particular task could be achieved. Some might work better than the other, even though it might not seem so.</b> It is worth trying each of them, in a sensible, time saving manner.
