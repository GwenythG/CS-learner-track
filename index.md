# Georgia Tech Industrial Engineering Student Blog

This is a blog by a Georgia Tech student studying a mutative skill set. It serves as a record of all the learning processes since July 2023 and acts as a searchable notebook for future reference. Also served Feynman's learning method by revising & retelling the course.

## Catalog

- [ISYE 6740 Computational Data Analysis](#ISYE 6740 Computational Data Analysis)
- [ISYE 7405 Multivariate Data Analysis](#ISYE 7405 Multivariate Data Analysis)
- [ISYE 6334 Probabilities in Supply Chain Engineering](#ISYE 6334 Probabilities in Supply Chain Engineering)
- [ISYE 6501 Intro to Analytics](#ISYE 6501 Intro to Analytics)

## Introduction

Welcome to my blog! I am a student at Georgia Tech, pursuing a degree in Industrial Engineering. This blog is dedicated to documenting my journey and sharing my experiences and knowledge with others.

## Purpose

The main purpose of this blog is to keep track of my learning progress. 

I will be sharing my insights, coding projects, and any interesting discoveries I make along the way. 

Additionally, I intend for this blog to serve as a valuable resource for myself and others. The content will be organized and easily searchable, allowing me to review concepts and find relevant information whenever needed.

## Topics Covered

Throughout this blog, I will cover a wide range of topics related to computer science. Some of the areas I plan to explore and discuss include:

- Programming languages, Skl-learn and Pytorch
- Databases skills, SQL
- Web development
- Artificial intelligence and machine learning
- Operations Research
- ......

## ISYE 6740 Computational Data Analysis

1. #### Minimize within-cluster square of sum method: K-means

   The distortion function using the squared Euclidean distance will lead to the cluster centers being defined as:
   $$
   \mu_k = \frac{\sum_{n} (r_{nk}x_n)}{\sum_{n} (r_{nk})}
   $$

​		To prove this, we will differentiate the distortion function J concerning μk and set the derivative equal to zero.
$$
J = \sum_n \sum_k (r_{nk} \lVert x_n - \mu_k \rVert^2)
$$
​		Using the chain rule, we have:
$$
\frac{\partial J}{\partial \mu_k} = \frac{\partial}{\partial \mu_k} \left(\sum_n \sum_k (r_{nk} \lVert x_n - \mu_k \rVert^2)\right)
$$
​		Now, set the derivative equal to zero:
$$
0 = \sum_n (r_{nk})(x_n - \mu_k)
$$
​		Now, let's isolate μk:

$$
0 = \sum_{n}(r_{nk})(x_{n} - \mu_{k})
$$
​		Now, divide both sides by 
$$
Σn(rnk)
$$

$$
0 = \frac{\sum_{n}(r_{nk})(x_{n} - \mu_{k})}{\sum_{n}(r_{nk})}
$$

$$
0 = \frac{\sum_{n}(r_{nk})(x_{n} - \mu_{k})}{\sum_{n}(r_{nk})}
$$

$$
0 = \frac{\sum_{n}(r_{nk})(x_{n} - \mu_{k})}{N_{k}}
$$

​		Now, we have:

$$
0 = \frac{\sum_{n}(r_{nk})(x_{n} - \mu_{k})}{N_{k}}
$$
​		Where Nk is the number of data points assigned to cluster k (i.e., Σn(rnk)). Now, multiply both sides by Nk:

$$
0 = \sum_{n}(r_{nk})(x_{n} - \mu_{k})
$$

$$
0 = \sum_{n}(r_{nk})(x_{n}) - \sum_{n}(r_{nk})(\mu_{k})
$$



Now, isolate μk:

$$
\sum_{n}(rnk)(\mu_k) = \sum_{n}(rnk)(x_n)
$$


Divide both sides by Σn(rnk):

$$
\mu_k = \frac{\sum_{n}(rnk)(x_n)}{\sum_{n}(rnk)}
$$


And this is exactly what we wanted to prove. The cluster center μk is given by:

$$
\mu_k = \frac{\sum_{n}(rnk)(x_n)}{\sum_{n}(rnk)}
$$
So, by minimizing the distortion function using the squared Euclidean distance, we indeed obtain μk as the center of the k-th cluster.









## ISYE 7405 Multivariate Data Analysis

## ISYE 6334 Probabilities in Supply Chain Engineering

## ISYE 6501 Intro to Analytics

### 1. Classification and Regression Models:

The regression tree does cluster first and gives different regression formulas y=a1x1+a2x2+...+anxn for each cluster, which needs enough amount of data points.

Random Forest does thousands of times regressions, then randomly separates subsets of features (variables y_n). Eventually, down to every leave, it contains the predicted value (average of all possible point values in the leaf) of object variable y_n. The regression formula would be simple (even constant y=a0). 

The difference between a regression tree (single tree) and a random forest (numerous trees) if you're fitting the regression tree to the average (**group by similar**):

**All the different features are branched in some certain points in random trees, but in the regression tree, features have to be fitted in limited boxes, which leads to the loss of information.**

you might lose information by taking the average and ignoring data points that are relatively small. Therefore, it might be wrong to give only 3 possible values of the coefficient because real life is of variety. 

However, it's ok if you only have 3 possible values in a random forest, because the metric is based on averaging a huge number of values in thousands of trees. There are distinct characters down to the leave, which is either calculated in one group of trees or another. Each tree is processed differently, 

The benefit of random forest is that if you're taking an average, it's likely to give a better prediction.

**i.e. How many hours should you, a student from MSA, study in different courses?**

variable counted: the extent of coding, the understanding of math, intuition,...

For a CS major, you might fall into one box that the coding coefficient is small (a1 value),

For an English major, you might fall into one box the coding coefficient is large (a1 value),

Think of a red guy who is doing fitting for himself from a data set that accounts for the blue guy and green guy: **Y_red=a0Y_blue+a1Y_green**

<img src="C:\Users\zuans\Desktop\CS-learner-track\assets\d5ef491d3c48096d48c534a7a21d74f.jpg" alt="d5ef491d3c48096d48c534a7a21d74f" style="zoom:20%;" />

The branch separates different features of blue and green guys by setting criteria. the green guy takes up more boxes because of the similarity to the red guy. Eventually, each leaf contains a value Y_red=c, and we cluster the values.

#### 2. Difference of Linear Regression and Logistics Regression

The model that tends to be unexplainable tends to be better.

| The situation where you want the model explainable:       |
| --------------------------------------------------------- |
| Need Approval (Based on reasoning, or from non-technical) |
| College/University/Graduate admissions                    |
| Financial regulations                                     |
| Sports team strategy                                      |
| Political/Policy decisions                                |
| Criminal justice......                                    |

| The situation where you don't even care: |
| ---------------------------------------- |
| Don't care "why"                         |
| LLMs, Chatgpt, etc.                      |
| predictive App                           |

| The situation where you prefer is  not explainable |
| -------------------------------------------------- |
| User Privacy concerns, ethical problems            |
| High volume of queries                             |
| General knowledge                                  |

#### The difference between Linear Regression and Logistic Regression:

**C: Will it rain tomorrow?**

Lin: How much rain will there be tomorrow?

Log: What's the probability it will rain tomorrow?

**C: Is the customer satisfied?**

Lin: How satisfied is the customer?

Log: How likely would the customer to purchase again?

Linear regression gives a continuous real number value, Logistics Regression gives a probability that ranges from 0-1, using the sigmoid function to fit z = β0 + β1*X1 + β2*X2 + ... + βn*Xn into P(Y=1|X) = 1 / (1 + e^(-z)).

We can conclude that linear regression is most suitable in Continuous number variables like house price, sales, etc. However, logistics regression are used to deal with binominal variables or multi-classification questions like predicting success, and giving yes/no answer.   

**How can I turn the Logistics regression model into the Classification Model?**
Setting threshold, i.e. setting probability >=0,5 as success, probability <=0.5 as unsuccess.

