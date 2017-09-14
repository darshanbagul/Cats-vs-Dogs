# Cats vs. Dogs

This repository comprises of my experiments on the Asirra (Animal Species Image Recognition for Restricting Access) data set containing images of Cats and Dogs. This project is my solution to the Kaggle competition [Dogs vs. Cats](https://www.kaggle.com/c/dogs-vs-cats) hosted in 2013. This dataset has become a main stream dataset to experiment with image classification techniques, where people used basic computer vision techniques combined with Deep Learning algorithms for achieving state of the art results. 

## Approach
For image classification, the primary task is to understand the images. Convolutional Neural Networks are the most popular with image related tasks, given their abilty to better understand spatial correlations in images. 

The dataset provided is a subset of the actual data set, and we have to tweak our solution in order to handle the limited dataset. Here is how I approached the problem:
  1. Data exploration and visualization for understanding the image characteristics
  2. Constructing a Convolutional Neural Network from scratch for Image classification
  3. Using Data Augmentation techniques for increasing the dataset
  4. Transfer Learning and fine tuning using pre-trained VGG 19 Network

## Asirra Dataset

Web services are often protected with a challenge that's supposed to be easy for people to solve, but difficult for computers. Such a challenge is often called a CAPTCHA (Completely Automated Public Turing test to tell Computers and Humans Apart) or HIP (Human Interactive Proof). HIPs are used for many purposes, such as to reduce email and blog spam and prevent brute-force attacks on web site passwords.

Asirra (Animal Species Image Recognition for Restricting Access) is a HIP that works by asking users to identify photographs of cats and dogs. This task is difficult for computers, but studies have shown that people can accomplish it quickly and accurately. Many even think it's fun!

Asirra is unique because of its partnership with Petfinder.com, the world's largest site devoted to finding homes for homeless pets. They've provided Microsoft Research with over three million images of cats and dogs, manually classified by people at thousands of animal shelters across the United States. We are able to obtain a subset of the data set that they have provided Kaggle for hosting this competition.

## Image recognition attacks

While random guessing is the easiest form of attack, various forms of image recognition can allow an attacker to make guesses that are better than random. There is enormous diversity in the photo database (a wide variety of backgrounds, angles, poses, lighting, etc.), making accurate automatic classification difficult. In an informal poll conducted many years ago, computer vision experts posited that a classifier with better than 60% accuracy would be difficult without a major advance in the state of the art. For reference, a 60% classifier improves the guessing probability of a 12-image HIP from 1/4096 to 1/459.

The current literature suggests machine classifiers can score above 80% accuracy on this task [1](http://xenon.stanford.edu/~pgolle/papers/dogcat.pdf). Therfore, Asirra is no longer considered safe from attack.

Let us try to improve upon the 80 % accuracy stated in the paper.

## Dataset organization

You can download the dataset [here](https://www.kaggle.com/c/dogs-vs-cats)

All you need is the train set

The recommended folder structure is:

Folder structure

    data/ 
      train/
        
        dogs/ 
            dog001.jpg
            dog002.jpg
            ...
        
        cats/ 
            cat001.jpg
            cat002.jpg
            ...
    
      validation/
        
        dogs/ 
            dog001.jpg
            dog002.jpg
            ...
        
        cats/
            cat001.jpg
            cat002.jpg
            ...
