---
layout: post
title:  "General Problem of Learning"
date:   2020-05-03 18:45:00 +0100
comments: True
share: True
categories: Learning
---

As a student of Machine learning there are various terms that are being thrown around in the community I would like to clarify on each of the terms and my opinion on how it will help solve the issue of Artificial General Intelligence which has remained the greater goal of the community. 

**Supervised learning**:

A term that is used to describe learning when a label is attached to a datapoint. For example an image with a dog as it's central object will be called an image of the dog. In a numerical data sense the label of a patient is sick or not when corresponding to their results is counted as a label. 

The issue with supervised learning is that it works very well but in most fields the labelling of images requires an expert to label the data. This is a very cost expensive process. Imagine if I want to learn about cracks in a metal and learn about patterns associated with it it requires an expert to label it. The same goes for medical images like scans etc.  

A corresponding thought experiment in the real human learning can be very simple. When we were kids we are shown an apple and then taught that's is how an apple looks like. We then taste the apple and extract features that each of us identify with an apple. Same with most items. We remember certain characteristics when come across a newer item and the next time we see it we identify it as the corresponding item. This is the task of classification. 

**Unsupervised learning**: 

Unsupervised learning is a process of learning structure from data. It has no labels attached and is mostly trying to learn the entire distribution and generalize from the learnt distribution. Unsupervised learning is most useful if and when cracked for many tasks since the world has lot of tasks which lack labels or labelling is very expensive. 

A good real life example will be to see that all species belonging to the cat family look alike but putting certain similar looking specie into similar category like lion, tiger. A more complicated task would be identifying tunes in a music without supervision or structures in movies. That is why unsupervised learning is a very challenging task in the machine learning domain as well. Even humans don't do very well in an unsupervised setting. (Some humans do well and they are geniuses). Since every human is not very well in such tasks expecting a similar thing from machine is a tough ask. 

**Self Supervised Learning**:

Self supervision is a learning method where the labels are being extracted from the data itself. It can be some correlation between the data or some transformation inflicted on data to get labels. In a machine learning sense this can be something like learning the context of an image i.e. if we have images of face and we see that nose is missing we learn with respect to the original image about how the nose fits in and learn the entire the data. 

In a recent discussion thread on twitter !<https://twitter.com/MelMitchell1/status/1256695232164323329?s=20> it was mentioned that Self supervision is a process where we use techniques of supervised learning to establish tasks of unsupervised learning. 

In my opinion this is a very natural setting that we as humans learn from. Imagine the situation where we are given a car to drive and we aren't told anything about what is a clutch, brake or accelerator. Or we dont know what is a gear. We just see some data and learn correlations. We know that pressing the accelerator moves the car, brake stops the car. But we can call it mover(accelerator), stopper(brake), clutch (speed changer). we establish the task of driving or atleast learning what each component means and its function without even knowing what each thing means. It means that we have learnt a unsupervised task of getting some structure without even getting the actual labels. 

**Reinforcement Learning**:

Reinforcement learning is a action reward based process. A good machine learning example is when a robot which is completely unaware of its environment learns by reward function i.e. if a machine bumps on something it gets a negative reward and if it goes well and reaches the target it counted as a sum of positive experiences. This is then optimized to make sure the robot always understands the environment and takes the most optimized path.

A good example of reinforcement in real life is learning driving. We learn not to bump at people brake and get a negative reward or bad consequence if we hit something or someone and we learn to optimize the path ourselves. A remark is that the robot takes a long time to optimize for the environment but humans adapt quickly. 

**Semi Supervised learning**: (By [Abhijeet Parida](http://abhijeetparida.ml/))

Semi-supervised machine learning tasks combine learning from small amounts of labelled data with a large amount of unlabeled data during training. The learning is a hybrid of both the supervised as well as unsupervised approaches. It is really useful in scenarios where a large amount of data is available but only a small fraction is actually labelled. The labelled data is used to provide a hint as to how the unsupervised algorithm should perform.


Even though applying the human ability of unsupervised learning we know that Cat, Dog, and Elephant are different distinct animals but we do not know their names ( due to no labels). When a child from a picture alphabet book is taught C for Cat, D for Dog, E for Elephant, looking at those labelled examples, next time it sees its pet cat, it can identify it as Cat.

**Weakly Supervised learning**:(By [Abhijeet Parida](http://abhijeetparida.ml/))

Weakly-supervised methods of learning are used when the labelled data are noisy or imprecise. The methods also deal with methods where the label are may be distantly related to the given task. For eg. in segmentation tasks, supervised methods require pixel-level annotation, but weakly-supervised methods can learn to segment from scribbles, points, bounding box, or class-level annotation.

When you come back from a trip to the African Savannah (tall brown grassland all around). You show your great-grandma photos of the numerous zebras, elephants, lions, and giraffes you saw (labels as in object detection). She never knew that these animals existed or ever seen a picture of them before. She borrows a photograph where most of the animals are present and she shows it to her friends over tea and says,”look this out here is a zebra. Look look this one is called a Lion.”(inference as in segmentation)

