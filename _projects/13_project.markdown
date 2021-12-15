---
layout: page
title: MNIST Fashion dataset Classification
description: A deep learning based classifier that would classify the objects in the Fashion MNIST dataset using Pytorch
img: /assets/img/fashion_mnist.jpg
importance: 3
category: Academic and Personal Projects
---
The main aim here was to build an artificial neural network based classifier that would help in the classification of objects (images) from the Fashion MNIST dataset. Pytorch was used for this. Each of the images in the dataset is a 28x28 pixel grayscale image, which when flattened gives a feature vector of length 784 each. Some of the sample images are as shown in the grid in Figure 1.

<div class="row justify-content-sm-center" >
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/fashion_mnist.jpg' | relative_url }}" alt="" title="example image"/>
            <div class="caption">
                FIGURE 1: SAMPLES FROM THE MNSIT DATASET
            </div>
        </center>
    </div>
</div> 

<h5><b>Data Preprocessing</b></h5>
Since Pytorch was used and dataset was a custom dataset, the __len__ and the __getitem__ methods that are inherited form the from Pytorch’s Dataset class were used for accessing the dataset. The __len__ method returns the complete length of the dataset that is being read. On the other hand, the __getitem__ accesses the data by index i.e, it accesses individual rows/samples in the dataset using the ‘index’ passed to it. In other words, it maps each row in the data to an index. 

As part of preprocessing, I also applied transforms and augmentations to the images, these are very important as they help prevent overfitting and also help expand the dataset, with more variation. One of the more important transformations that help are scaling, especially, when it comes to images. Pixels range from 0 to 255 in their numeric values, and using these values without any normalization will cause the gradients to explode in some cases and become zero at other times. Hence, to avoid this, normalilzation is a must.

<h5><b>Network Initialization</b></h5>
I learnt that initialization plays a very important role in deep learning. If the initilization is very bad, then the model might get stuck at a local minimum and might not give good accuracy. On the other hand, if the initilization is good, the model might coverge at a better minimum, giving good accuracy. In this problem, the Xavier intilization worked better than the normal random initialization of the model. 

<h5><b>Training and Testing</b></h5>
Once the above tasks were complete, I trained the model. Tuning had to be performed for hyperparameters such as the learning rate, the number of neurons in each layer etc. Also, the learning rate had to be reduced once in a while when the accuracy/loss would not improve much. Finally, the model had to be tested on unseen data. The final accuracy achieved was around 87%, with the use of Xavier initialization, transforms and augmentations. 

<h5><b>Visualization</b></h5>
Along with the visualization of the accuracy loss, the incoming weights for a node in the second layer of the neural network was visualized. It was observed that the incoming weights at each node somehow represents a pattern. It is amazing to see that the neurons learn some specific feature, as show below! Figure 2 shows the progressions of the incoming weights of the 50th node in the second layer over a range of 20 epochs. It can be seen that the patter it is looking form looks like a shirt/t-shirt (both of which were there in the dataset) . 


<div class="row justify-content-sm-center" >
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/nn_visualization.jpg' | relative_url }}" alt="" title="example image"/>
            <div class="caption">
                FIGURE 2: WEIGHT VISUALIZATION OF THE 50TH NODE IN THE SECOND LAYER
            </div>
        </center>
    </div>
</div> 
