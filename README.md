# CAPTCHA-Recognition-Models
The following two Python models aim to solve captcha images using Convolutional Neural Networks (CNN) and Residual Neural Networks (ResNet). These models are trained to predict the five characters in our captcha image dataset. Captchas are commonly used to test whether an online user is human by having them solve images with letters that are not easily recognizable to bots. Below is a simplified breakdown of the code’s functionality and data preparation:  

-----------------------

**Data Preparation:**

• The code mounts to our Google Drive to access our CAPTCHA dataset. The dataset used to train our models can be found here: https://www.kaggle.com/datasets/parsasam/captcha-dataset/data?select=114ty.jpg

• It then loads each .jpg image from the directory.

• A pre-processing function converts the images to the RGB color space and normalizes the image's pixel values.

-----------------------

**Model Architecture:**

• A CNN model is created with layers designed for feature extraction and classification.

• The model includes convolutional layers, max pooling, a flattening step, dense layers, and dropout for regularization.

• The output layer is structured to predict five characters, these characters can be lowercase letters, uppercase letters, or numbers. In total, there are 62 possibilities for each of the five characters.

• The RestNet model uses ResNet50, a pre-trained convolutional neural network trained on ImageNet.

• Custom dense layers are added. These include a dense layer with 512 units and ReLU activation, a dropout layer for regularization, and a dense layer. This is reshaped to match the expected format.

-----------------------

**Training Process:**

• The dataset is split into training, validation, and testing sets.

• Both models use the Adam optimizer and categorical cross-entropy loss function.

• Training occurs for 100 epochs.

-----------------------

**Evaluation and Testing:**

• After training, the model’s accuracy and loss are evaluated on the test set.

• A random CAPTCHA image from the test set is chosen, and the model predicts the characters for that image. This gives a realistic simulation for running our model on a website's captcha image.

• The predicted characters are then compared to their true labels, displaying the accuracy for each character.

-----------------------

**Problems encountered:**

Our original dataset contained over 113,000 CAPTCHA images but uploading all of the images on Google Drive and loading them onto Google Collab proved to be a challenging task. Due to this, our programs were run with only 3000 images, possibly explaining the low accuracy score. 

-----------------------

**Future Improvements:**

We would run the program outside of the Google Collab environment and without Google Collab in order to have access to the entire dataset. This would likely increase the program’s accuracy score. 

-----------------------

**Evaluation:**

The following figures used the trained model on a randomly selected image from our test set. The predictions and labels are displayed below.

**CNN Captcha Prediction:**
![image](https://github.com/Isaiahensley/CAPTCHA-Recognition-Models/assets/143129356/11bcb1bd-e073-4897-8219-fd3200b47823)

**ResNet Captcha Prediction:**
![image](https://github.com/Isaiahensley/CAPTCHA-Recognition-Models/assets/143129356/0ef614af-4ea7-4ddc-818d-3ec2ea746a01)

-----------------------

**Accuracy Scores:**

The following graph compares the CNN and ResNet model's loss and accuracy. We’ve also provided screenshots for each model's accuracy score.

![image](https://github.com/Isaiahensley/CAPTCHA-Recognition-Models/assets/143129356/b9abe38c-f351-4941-ac33-9978ca7c04a2)

**CNN**
![image](https://github.com/Isaiahensley/CAPTCHA-Recognition-Models/assets/143129356/7c35e024-a3df-44a6-8b8d-cb2f1c1fa3a3)

**ResNet**
![image](https://github.com/Isaiahensley/CAPTCHA-Recognition-Models/assets/143129356/82736ad6-8b78-4db3-8f23-409421d85b2e)
