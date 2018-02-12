# Lecture 0-1: Introduction of Machine Learning

[toc]

# What we expect to learn from this course?

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/1.png)

Artificial Intelligence (AI) aims to make machines as smart as human beings. But for long, people don't know how to do this.

Until 1980s, machine learning (ML) comes into beings. Just like its name, machine learning aims to make **machine learn to learn.**

Q1: *what is the relationship between AI and ML?*

A: ML is a potential way to achieve AI.

Q2: *what is the relationship between ML and deep learning (DL)?*

A: DL is one of methods of ML.

- Extension: Creature's Instinct: Beaver Build Dam

Beavers are born with the instinct to move stones to build dams as long as they hear the sounds of water flows.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/2.png)

This can be summarized to a rule for beaver: When hear the sounds of water flows, build dam!

**Compare it with Human Being's Instinct**

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/3.png)

- AI is just some "if"s ?

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/4.png)

No, it's not what we are chasing in the course!

# What is Machine Learning ?

- Do Speech Recognition

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/5.png)

- Do Image Recognition

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/6.png)

## ML mostly equal to Looking for a Function

True function to do perfect speech recognition is too complex, there are efforts starting from 1960s trying to write enough rules to include all mappings from voice to word, however it's still not finished yet! So we need machine to help us find out the function **From Data**.

To simplify, we let machines try to find the true function using training data we give them. After that, machines would give response to new input data we give to them based on rules that they have learned from training.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/7.png)

## How to find this function: Framework

**Example: Image Recognition**

First, we have **a set of function**. (This set is called **Model**)

Then, we have **training data**, they consist of some input & output pairs, respectively used as function input and function output. (This method also known as **Supervised Learning**)

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/8.png)

- How to find the true function from the set?

We need a good algorithm to find the best function ($f^*$function that has greatest goodness).

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/9.png)

After we find the best function $f^*$, **how can we make sure that a machine can recognize the cat in a picture that it has never seen before?**  Well, that is exactly one of the most important problem in ML, that is: **can machine draw inferences?**

- Three Steps to do ML

1.Determine a function set;

2.Enable machines to measure how good a function is;

3.Give machines an algorithm that can help pick the "best" function.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/10.png)

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/11.png)

# Learning Map

- What ML technics you can learn from this course ?

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/12.png)

Next, we give a simple introduction to conceptions included in the map.

## Regression

Definition: The output of function that machine is trying to learn is a scalar.

Example: Predicting PM2.5

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/13.png)

## Classification

Two types:
- Binary Classification: output Yes or No
- Multi-class Classification: output i (i$\in${1,2,3,..,N})

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/14.png)

Example for binary classification: Gmail filter Spams

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/15.png)

Example for multi-class classification: Document Classification

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/16.png)

## Model

**Different model = Different set of functions -> Different Performance of machine**

### Linear Model

### Non-linear Model

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/17.png)

Deep Learning is one of Non-linear models. When doing deep learning, it usually means that the goal function is very very complex, **and therefore it can also complete complex tasks such as image recognition, playing GO!**

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/18.png)

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/19.png)

All technics mentioned above belong to field of **Supervised Learning**, it usually comes with great quantities of training data. These training data are some input/output pairs of target function, and normally the output need to be manually labelled, so the function output is also called label.

*Then, how to collect a large amount of labelled data？*

A: Semi-supervised Learning.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/20.png)

## Semi-supervised Learning

**Unlabelled data can also help machine learning!**

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/21.png)

## Another way to save data: Transfer Learning

(labelled/unlabelled) Data that are not directly linked with goal problem may be helpful to the goal problem.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/22.png)

## What can machine learn without label: Unsupervised Learning

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/23.png)

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/24.png)

- Machine creates new animals after seeing some animal images

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/25.png)

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/26.png)

## Structured Learning: Output Result with Structure

In speech recognition: input - a voice clip, output - corresponding sentence.

In translation: input - Chinese sentence, output - English sentence.

In object detection: input - images, output - boundary of object.

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/27.png)

Usually, many people heard of regression and classification, but seldom heard of Structured Learning, even textbooks may ignore it.

However, structured learning is a very important part of ML field!

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/28.png)

## Reinforcement Learning

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/29.png)

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/30.png)

- Supervised v.s. Reinforcement 

Supervised: Have a supervisor to teach machine; (Learning from teacher)

Reinforcement: Let machine to explore and teach itself. (Learning from critics)

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/31.png)

So Reinforcement Learning is closer to how human beings learn.

**Example: Plying GO**

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/32.png)

# Relation between Terminomogy

![](http://tech-blog-pictures.oss-cn-beijing.aliyuncs.com/MachineLearningMoocNotes/Lecture0-1/33.png)

**Data you have determines what scenario your problem is in, the type of your problem defines its task, and we can use different models (methods) to solve same problems.**


































