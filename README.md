# Computer Vision Age Verification
## Project Overview
Computer vision model predicting customer age from facial images using deep learning (Validation MAE: ~7.6 years).

---

## Business Problem
A chain of supermarkets sell alcohol and other age-restricted products. Cashiers must verify that customers meet legal age requirements before completing these purchases. However, manually checking IDs for every customer can slow down checkout lines and introduce human error.

The goal of this project is to develop a computer vision model capable of estimating a customer's age from a facial image. This system could assist store employees by flagging customers who may be under the legal age threshold and require ID verification.

---

## Business Objective
The objective is to build a deep learning model that predicts a customer's age based on their facial image. By integrating such a model into store checkout systems, the stores could improve efficiency while maintaining compliance with age verification laws.

Possible benefits include:

- Faster checkout experiences
- Reduced human error in age estimation
- Automated flagging for ID checks
- Improved compliance with legal age restrictions
- Data gathered for future anaylsis and exploration

---

## Dataset
The dataset consists of facial images labeled with the age of each individual.

The data is organized into two primary components:

- **labels.csv** — contains the age label for each image  
- **final_files/** — directory containing facial images of customers  

The dataset was used to train and validate a deep learning model capable of learning visual patterns associated with aging.

---

## Exploratory Data Analysis (EDA): Key Insights

Initial analysis of the dataset revealed several useful observations:

- The dataset contains thousands of labeled facial images
- Ages range from 1 - 100 years old
- Shoppers between the ages of 1 and 60 made up the majority of customers.
- The number of customers under the age of 21 were well over double the number of customers that were 21 and older
- Images contain natural variation in lighting, orientation, and facial expressions

These characteristics help train the model to generalize to real-world checkout environments.

---

## Model Development

To predict age from images, a **Convolutional Neural Network (CNN)** architecture was implemented using **TensorFlow/Keras**.

Key steps in the modeling process included:

1. Loading and preprocessing image data using **ImageDataGenerator**
2. Rescaling pixel values for normalization
3. Splitting the dataset into **training and validation sets**
4. Using a **pretrained ResNet50 architecture** as the feature extraction backbone
5. Adding fully connected layers for age regression
6. Training the model across multiple epochs while monitoring validation performance

The model predicts a **continuous age value**, making this a **regression task** rather than classification.

---

## Model Performance

| Metric | Result |
|------|------|
| Validation MAE | ~7.6 years |

A **Mean Absolute Error (MAE) of approximately 7.6 years** means that, on average, the model’s predicted age differs from the true age by about 7–8 years.

While this level of accuracy may not determine exact ages, it is **sufficient to flag potentially underage customers** for further verification.

---

## Practical Application

The trained computer vision model could be integrated into Good Seed’s checkout process to assist employees with age verification.

A potential workflow could include:

1. A camera at checkout captures a customer's facial image.
2. The trained model estimates the customer's age.
3. If the predicted age is below a predefined threshold (for example 25), the system alerts the cashier.
4. The cashier requests identification before completing the purchase.

This system would not replace human verification but instead support employees by identifying customers who may require ID checks. By leveraging computer vision and deep learning, the model improves the efficiency and reliability of age verification in retail environments. While it does not determine exact ages, it provides a useful screening tool that helps employees quickly identify customers who may require ID verification.
