---
layout: page
title: SVM's for the Molecular Biology Data Set
description: An SVM classifier for the Molecular Biology (Splice-junction Gene Sequences) Data Set
img: /assets/img/svm_cover1.JPG
importance: 5
category: Academic and Personal Projects
---

The dataset used was the Molecular Biology (Splice-junction Gene Sequences) Data Set from UCI's machine learning repository. The problem posed in this dataset was to recognize, given a sequence of DNA, the boundaries between exons (the parts of the DNA sequence retained after splicing) and introns (the parts of the DNA sequence that are spliced out). The dataset thus, had 2 target classes and 60 features. The SVM solves an optimization problem and hence, the CVXOPT library was used to solve the convex quadratic problem, to obtain an accurate decision boundary between the two classes. 

<h5><b>Data preprocessing</b></h5>
The dataset had 2175 training samples and 1000 test samples. Because the SVM is a maximum margin classifier, features scaling (mean normalization) had to be used, so that the features with larger values would not affect the distance metric differently than the smaller ones. This was the only preprocessing required

<h5><b>Training, Implementation, Testing</b></h5>
The CVXOPT library was used to solve the convex optimization problem. The solver in this library had a specific input format for inputting the equations and the constraints. Once inputted in the right format, the solver would solve the convex quadratic problem and output the paramters of the decision boundaris. Hyperparameter tuning was also performed for the tradeoff parameter 'C' (The parameter that decides the amount of slack that can be allowed). The final accuracy for the classifier with the best hyperparamter, chosen using 5 fold cross validation 84.7%.
