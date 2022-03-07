# Pneumonia-Detection-From-Chest-X-Rays
A Convolutional Neural Network that will detect the presence of Pneumonia on a Chest X-ray.

### Table of Contents
1. Project Motivation
2. Installations
3. File Descriptions
4. How To Interact With the Project
5. Licensing, Authors, Acknowledgements

### Project Motivation:
The goal of the project is to create an algorithm that is able to identify the presence of Pneumonia is radiological chest X-rays. Pneumonia is an infection that leads to inflammation in one or both lungs. The disease may lead to mild to severe illness in individuals.

The Pneumonia Detection Algorithm will be designed to detect the presence of pneumonia in X-ray radiographic imaging and assist clincians in diagnosing the aformentioned condition. The medical device falls under the Class II, and is considered a medium risk. The algorithm provides Computer-Assisted Diagnosis for clincians. An application for 510k is necessary for FDA regulatory approval.

### Installations:

The following libraries will be required for the project.

1. Io
2. Glob
3. Numpy
4. Keras
5. Pandas
6. Sklearn
7. Tensorflow

### File Descriptions:
There are three main files - Build and train model.ipynb, EDA.ipynb, Inference.ipynb. These notebooks contain the majority of the code necessary for the project. The first notebook is used to create and save the model. The second file is used for exploratory data analysis on the metadata of the dataset. The third notebook contains the code for model inference on a new image.

The model can be found in the final_model.json file. The weights could not be loaded onto Github due to the size of the file.

Finally, the submission template for the Food and Drug Administration can be found at FDA_Submission_Template.md file. Here, a summary of the algorithm can be found.

### How To Interact With the Project:
The notebooks can be viewed to assess the code and outputs for the project. The code can be converted into a python file for scripting and utilization in real-world scenarios.

### Licensing, Authors, Acknowledgements
- NIH. (December 2017). NIH Chest X-rays. Retrieved 06 March 2022 from https://www.kaggle.com/nih-chest-xrays/data
- Rajpurkar, P., Irvin, J., Zhu, K. and Yang, B., 2017. CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays with Deep Learning. 3rd ed. Cornell University: arXiv.
