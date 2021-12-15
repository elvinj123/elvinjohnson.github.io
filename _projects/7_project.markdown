---
layout: page
title: Crawlbot
description: A Data Crawler to identify websites on given keywords from the web in areas of child and woman abuse, cyber bullying, etc.
 
img: /assets/img/crawlbotcover.jpg
# redirect: https://unsplash.com
importance: 2
category: Academic and Personal Projects
---

This project was completed as part of the Smart India Hackathon, which was a nationwide hackathon, organized by the Government of India. The objective/problem statement my team and I had to work on was to create a crawler to crawl the Web and to identify websites that contained material pertaining to cyberbullying, woman and child abuse. We made it to the finals of the event. 

My teammates worked on the crawler that would efficiently crawl the web and extract textual content as well as the web interface to display the results dynamically. My role was to build a language based text classifier that would perform two tasks. First, it would classify the text in the link of the website and second, it would classify the text present on the website, both of which are outputted by the crawler. The classifier was a binary classifier that would tell if the website was malicious or safe. 

<h5><b>Data Preprocessing</b></h5>
The data used had textual data of both the classes, i.e normal text as well as text pertianing to cyberbullying and abuse. The following steps were carried out.
1. Lowercasing: Convert all text to lower case             
2. Tokenization: Convert the sentences into a list of words
3. Stop words removal: Remove irrelevant words like 'a', 'the' etc       
4. Lemmatization: Reduce words to their base tense. Eg 'cooking', 'cooked', 'cook' would all be converted to 'cook'          

Once the data was preprocessed the next step carried out was to convert each data sample into the 'bag of words model'. That is, the most frequent words occuring in both classes (around the first 1000 most frequent) would be picked up and the count of each of these words in each sample would be recorded, resulting in a vector of length 1000 for each data sample.

<h5><b>Training</b></h5>
Once the dataset was preprocessed and made ready, the next step was to train models. Various classification models like SVM's, Naive Bayes were trained and tested. Apart from this, I also trained an ANN model with a few layers. Hyperparamter tuning was also performed for all these models. In the end, the deep learning based ANN model was found to be the most acccurate of all the three, and thereafter, it was integrated into the crawler. Another state of the art language model called Xlnet was also trained, which also performed almost as good as the ANN. However, the ANN model was much more faster with its prediction as it was much more lightweight as comapred to the Xlnet model, and its accuracy was 97% on the test set. Following are the accuracies of a few of the models that were trained.  
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <center>
            <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/crawlbot_accuracy_table.jpg' | relative_url }}" alt="" title="example image"/>
        </center>
    </div>
</div>
<div class="caption">
    FIGURE 1: TRAINING/TESTING ACCURACIES
</div>



