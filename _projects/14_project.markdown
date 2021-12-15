---
layout: page
title: Decision Tree for Spotify Data
description: The goal this problem was to create a decision tree classifier to predict whether an individual would like or dislike a song based on a list of features.
img: /assets/img/spotify tree.jpg
importance: 4
category: Academic and Personal Projects
---

In this data set, an individual has generated a list of songs, each with a set of features, and whether the individual liked or disliked the song. The goal of this problem is to create a classifier to predict whether this individual would like or dislike a song based on a list of features.

<h5><b>Key Takeaways</b></h5>
Decision trees were used for this classification problem

<h6><b>Feature selection</b></h6>
Some features can be removed by using intuition and common sense but not all of them should be removed using this strategy. There might be a hidden relationships between features and the output variable. I realized this when I removed a few feautres based on intuition before training, and later calculated the feature importances of each feature (including the ones removed). It was noted that not all of my intuitions were true.

<h6><b>Hyperparameter tuning is essential</b></h6>
Decision trees can have a lot of parameters and validation is important. In this case, I had used 5 fold-cross validation and grid search for finding the best hyperparameters. There were hyperparamters like the criterion, maximum depth of the tree, the maximum leaf nodes etc 

The final accuracy achieved was 80%. Figure 1 is a visualization of the final decision tree
 

<div class="row justify-content-sm-center" >
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/spotify tree.jpg' | relative_url }}" alt="" title="example image"/>
        <div class="caption">
            FIGURE 1: FINAL DECISION TREE
        </div>
    </div>
</div> 