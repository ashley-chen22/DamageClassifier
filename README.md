# DamageClassifier

## Overview
Our proposed BuildingGAN works to enhance classification of disaster type and level of building damage. This is done by using DisasterGAN (model by Rui et al.) locally by cropping out images of the buildings and using these as our inputs.

By doing this we hope to address class imbalances as disaster type is dominated by 'fire' instances with very few 'volcano' and damage level is  dominated by 'no damage' and very few 'damaged.'  

## Data
Dataset used: xBD via xView2 challenge https://xview2.org/dataset

Examples of the data: 

<img width="353" alt="Screenshot 2025-05-10 at 10 34 46 AM" src="https://github.com/user-attachments/assets/6cd50fca-c07a-4837-9e0b-a559ca1b2e64" />

Diagram from https://arxiv.org/abs/1911.09296

## Files

EDA + PREPROCESSING
- UnderstandingDataFormat.ipynb
- xBD-to-Dataframe.ipynb
- BuildingGAN_Preprocessing.ipynb

GAN MODELS
-  VanillaGAN.ipynb
-  DisasterGAN.ipynb
    -->  Image_Generator.ipynb
-  BuildingGAN.ipynb
    -->  Image_Generator.ipynb
    --> BuildingGAN_Image_Generator.ipynb (able to generate more than one image at a time)

CLASSIFICATION
- ResNet50-Prototype.ipynb
- Resnet18_PostClassifier.ipynb

## Results
Sample output from VanillaGAN:

<img width="390" alt="Screenshot 2025-05-10 at 10 38 15 AM" src="https://github.com/user-attachments/assets/a8f2221d-e8f3-4147-a11c-4a13f338e242" />

Sample output from DisasterGAN:

<img width="781" alt="Screenshot 2025-05-10 at 10 39 00 AM" src="https://github.com/user-attachments/assets/1e83c7bb-bd3f-4f34-8206-9c1e870ab117" />

Sample out from BuildingGAN: 

<img width="888" alt="Screenshot 2025-05-10 at 10 39 20 AM" src="https://github.com/user-attachments/assets/9f1acf6f-6cdf-4c1f-bef8-c20ce3d350f8" />

ResNET-50 Classification of Disaster Type: 

0.780 accuracy on the cropped building images, no images from BuildingGAN

0.5695 accuracy on supplemented building image set

## Future Work 

Further tuning of BuildingGAN

Explore the potential of our GAN getting worse at generalizing

Using a different architecture for classification, also using metrics beyond accuracy (Recall, precision, etc.)

## Citations: 

"DisasterGAN: Generative Adversarial Networks for Remote Sensing Disaster Image Generation" by Rui et al. (https://www.mdpi.com/2072-4292/13/21/4284)



