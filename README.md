📊 CIFAR-10 Image Classification using Custom Neural Network Architecture

📌 Overview
This project implements a custom neural network architecture for image classification on the CIFAR-10 dataset using PyTorch. The architecture follows a specific design involving weighted combinations of parallel convolutional layers and aims to achieve high accuracy through systematic training and hyperparameter tuning.

📂 Dataset
Dataset: CIFAR-10

Description: 60,000 color images (32x32x3) across 10 categories (airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck).

Training Set: 50,000 images

Testing Set: 10,000 images

🏗️ Architecture
1. Intermediate Block
Consists of L parallel convolutional layers.

Each layer processes the same input image independently.

Outputs are weighted by learnable coefficients a1, a2, ..., aL, obtained from a fully connected layer.

Final block output:
x' = a1*C1(x) + a2*C2(x) + ... + aL*CL(x)

2. Output Block
Takes the final image from the last intermediate block.

Computes per-channel averages to form input to fully connected layers.

Outputs a logits vector for classification.

🖼️ Architecture Diagram
css
Copy
Edit
Input → [B1] → [B2] → ... → [BK] → [Output Block] → Logits
🏋️‍♂️ Training
Loss Function: Cross-Entropy Loss

Input Shape: (Batch Size, 3, 32, 32)

Output Shape: (Batch Size, 10)

Optimization: SGD/Adam (tuned via experiments)

Training Techniques: Batch normalization, dropout, learning rate scheduling, data augmentation.

🚀 Experiments & Results
Initial implementation tested with basic hyperparameters.

Progressive improvements by tuning:

Learning rates

Batch sizes

Number of blocks and layers

Regularization techniques

Evaluated using:

Training Loss per Batch

Training & Testing Accuracy per Epoch

Best Test Accuracy Achieved: XX%

📊 Plots
Training Loss vs. Batches

Accuracy vs. Epochs (Train & Test)
