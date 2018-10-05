# ML_Multi-class_Classification

In this project, I implemented the one-vs-all logistic regression to recognize the hand-written digits.

Automated handwritten digit recognition is widely used today, for example recognize the zip codes on mail and so on. 

First we need to extend the binary logistic regression as showed in the ML_Logistic Regression to the one-vs-all.

### 1. What‘s in the dataset?

In ex3data1.mat which contains 5000 training examples of handwritten digits.

Each training example is a 20 pixel by 20 pixel grayscale image of the digit. Each pixel is represented by a floating point number indicating the grayscale intensity at
that location. The 20 by 20 grid of pixels is **“unrolled”** into a 400-dimensional
vector. Each of these training examples becomes a single row in our data
matrix X. This gives us a **5000 by 400 matrix** X where every **row** is a training
example for a handwritten digit image.

The second part of the training set is a 5000-dimensional vector y that
contains labels for the training set. And it has mapped the digit zero to the value ten to make the data more compatible for Matlab.

### 2. Visualizing the data

The following fig contains 100 the random selected digit in the dataset:

<p align="center">  <img src="https://github.com/BMDroid/ML_Multi-classClassification/blob/master/figs/data.png" width="50%">
</p>     

### 3. Cost function and gradient

Because there are 10 classes for 10 different digits, so I need to train 10
separate logistic regression classifiers. 

The **cost function** is:

<p align="center">  <img src="https://github.com/BMDroid/ML_Multi-classClassification/blob/master/figs/cost_func.png" width="45%">
</p>    

and the **gradient** is:

<p align="center">  <img src="https://github.com/BMDroid/ML_Multi-classClassification/blob/master/figs/gradient.png" width="30%">
</p>    

To avoid the overfitting, we need to implemented the regularized the cost function and its gradient:

**Regularized cost function**:

<p align="center">  <img src="https://github.com/BMDroid/ML_Multi-classClassification/blob/master/figs/cost_func_r.png" width="55%">
</p>   

and the **regularized gradient**:

<p align="center">  <img src="https://github.com/BMDroid/ML_Multi-classClassification/blob/master/figs/gradient_r.png" width="45%">
</p>

### 4. One-vs-all

In oneVsAll.m, we need to train one classifier for each different digit. In particular, it returns all the classifier parameters in a matrix , where each row of Θ corresponds to the learned logistic regression parameters for one class. 

### 5. Training

Here, we use **fmincg**, a built-in function in the Matlab, which works similarly to the **fminunc**.

And our training accuracy is: 94.760000%.

