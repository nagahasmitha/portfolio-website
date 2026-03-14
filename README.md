A Robotics-Inspired Framework for Evaluating Adversarial Robustness of Deep Image Classification Models
Overview
Deep learning models, especially Convolutional Neural Networks (CNNs), are widely used in robotic perception systems and autonomous decision-making. However, these models are vulnerable to adversarial attacks, where small, carefully crafted perturbations to input images can cause incorrect predictions.

This project investigates the robustness of CNN-based image classification models against different adversarial attack techniques.

Using the CIFAR-10 dataset, we generate and evaluate adversarial examples using multiple attack strategies and analyze how these attacks affect model performance.

The framework introduces a Robotics-Inspired System Pipeline that validates predictions before applying adversarial perturbations, allowing accurate evaluation of attack impact.

Objectives
Study vulnerabilities of CNN models to adversarial attacks

Implement multiple adversarial attack methods

Evaluate robustness using quantitative metrics

Analyze perceptual similarity of adversarial images

Dataset
This project uses the CIFAR-10 dataset, which contains:

60,000 color images

10 object classes

32 × 32 image resolution

Example classes include:

Airplane

Automobile

Bird

Cat

Deer

Dog

Frog

Horse

Ship

Truck

CNN Model Architecture
A custom Convolutional Neural Network (CNN) is implemented for image classification.

Typical layers include:

Convolutional Layers

ReLU Activation

Max Pooling

Fully Connected Layers

Softmax Output Layer

The model is trained on the CIFAR-10 dataset to achieve high baseline accuracy before applying adversarial attacks.

Adversarial Attack Methods
The project evaluates four different adversarial threat models:

1. Fast Gradient Sign Method (FGSM)
A single-step gradient-based attack that perturbs the input image in the direction of the loss gradient.

Advantages:

Fast

Simple to implement

2. Projected Gradient Descent (PGD)
An iterative attack method considered a strong benchmark for adversarial robustness testing.

Features:

Multiple gradient updates

Stronger perturbations than FGSM

3. GAN-Based Adversarial Attack
A Generative Adversarial Network (GAN) is used to generate adversarial examples that fool the CNN classifier.

Advantages:

Produces realistic adversarial samples

Harder to detect

4. Hybrid Attack (GAN + PGD)
A combined attack strategy that merges GAN-generated perturbations with iterative PGD optimization.

This produces highly effective adversarial examples capable of significantly reducing model accuracy.

Robotics-Inspired System Pipeline
The framework includes a perception validation stage:

Input image is passed through the CNN.

Only correctly classified images are selected.

Adversarial attacks are applied.

The model prediction is evaluated again.

This ensures that the evaluation measures true adversarial vulnerability, not errors caused by misclassification.

Evaluation Metrics
The following metrics are used to analyze attack effectiveness:

Attack Success Rate (ASR)
Percentage of adversarial samples that successfully cause misclassification.

Accuracy Drop
Difference between baseline model accuracy and accuracy after adversarial attack.

Structural Similarity Index (SSIM)
Measures visual similarity between original and adversarial images to ensure perturbations remain imperceptible to humans.

Experimental Results
The experiments demonstrate that:

CNN models achieve high baseline accuracy on CIFAR-10.

Even small perturbations can significantly reduce model accuracy.

Iterative attacks like PGD and Hybrid attacks are more effective than FGSM.

Adversarial noise can cause critical failures in robotic perception systems.

Example Results
Original vs Adversarial Samples
Input Image Example:


Adversarial Output Example:


(Additional attack results for FGSM, PGD, GAN, and Hybrid models are included in the repository.)

Technologies Used
Python

PyTorch / TensorFlow

NumPy

Matplotlib

CIFAR-10 Dataset

Deep Learning

Adversarial Machine Learning

Future Improvements
Implement adversarial defense mechanisms

Test robustness on larger datasets (ImageNet)

Deploy the framework in real robotic perception systems

Develop real-time adversarial detection

Author
Naga Hasmitha
B.Tech – Computer Science and Engineering (Artificial Intelligence)
Amrita Vishwa Vidyapeetham
