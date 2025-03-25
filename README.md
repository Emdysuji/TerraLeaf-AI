# TerraLeaf-AI
 Deep learning-based plant disease classification system with specialized models for 10 plant species, identifying 3-6 diseases per plant. Aimed at enhancing agricultural productivity and sustainability.

# Overview
Plant Disease Classification is a machine learning project that leverages individual, plant-specific models to accurately diagnose diseases across 10 different plant species. Each model is uniquely designed and trained to classify 3–6 diseases for the plant it serves, providing a specialized, high-accuracy solution to aid farmers, botanists, and agronomists in disease identification and early intervention.

# Why It’s Important 🌍
Plant diseases can have devastating impacts on crop yields and food security. By using deep learning to classify diseases early, this project aims to:

- Help minimize crop losses.
- Enable precise disease management.
- Reduce the need for chemical treatments, promoting sustainable agriculture.

# Key Features
- Multi-Model Structure: Each plant species has its own dedicated model, fine-tuned to its unique disease characteristics.
- High Disease Detection Accuracy: Each model classifies between 3 to 6 diseases specific to its plant, trained with thousands of labeled images for robust detection.
- Scalable Design: The architecture allows for easy addition of new plant models or diseases as they become relevant.
- Real-Time Results: Efficient deployment on [insert platform, e.g., web, mobile] for immediate feedback to users.
  
# Supported Plants and Diseases
Plant Species |	Number of Diseases |	Example Diseases |
--------------|--------------------|------------------|
Apple         |	7                  | alternaria leaf spot, black rot, brown spot, gray spot, healthy, rust, scab|
Banana        |	7                  | Bract Mosaic Virus, Fungal Infection, Healthy, Insect Damage, Moko Disease, Panama Disease, Sigatoka Disease|
Beans         | 3                  | angular leaf spot, bean rust, healthy|
Cassava       |	5                  | bacterial blight, brown streak disease, green mottle, healthy, mosaic disease|
Grape         |	4                  | Black rot, Esca (Black Measles), Leaf blight (Isariopsis Leaf Spot), healthy|
Groundnut     | 5                  | early leaf spot, healthy leaf, late leaf spot, nutrition deficiency, rust|
Maize(Corn)   | 4                  | Cercospora leaf spot Gray leaf spot, Common rust, Northern Leaf Blight, healthy|
Tomato        |	10                 | Bacterial spot, Early blight, Late blight, Leaf Mold, Septoria leaf spot, Spider mites Two-spotted spider mite, Target Spot, Yellow Leaf Curl Virus, Tomato mosaic virus, healthy|
Potato        | 3                  | Early_blight, Late blight, healthy|
Rice          | 4                  | Rice Brown spot, Rice Healthy, Rice Hispa, Rice Leaf blast|


Note: The full list of plants and diseases can be found in the data/plant_disease_info.md file.

# Model Architecture and Training
Each model in this project is built using a deep convolutional neural network (CNN) architecture, optimized for image classification in TensorFlow. The models were trained using a dataset of [insert number] images, sourced from publicly available datasets and labeled with expert assistance.

- Architecture Highlights
- CNN Layers: Includes [number] layers optimized for feature extraction.
- Data Augmentation: Used to enhance model generalization and performance on unseen data.
- Custom Loss Function: Tailored for multi-class disease classification.

# Installation
To get started with this project locally, follow these steps:

- 1. Clone the repository:
git clone https://github.com/yourusername/PlantDiseaseClassification.git
cd PlantDiseaseClassification
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Download Model Weights: Download pre-trained weights from [link to weights] and place them in the models/ directory.
