# FDA  Submission

**Daniel da Cruz**

**Pneumonia Detection Algorithm**

## Algorithm Description 

### 1. General Information

**Intended Use Statement:** 
The Pneumonia Detection Algorithm is designed to detect the presence of pneumonia in X-ray radiographic imaging and assist clincians in diagnosing the aformentioned condition. The medical device falls under the Class II, and is considered a medium risk. The algorithm provides Computer-Assisted Diagnosis for clincians. An application for 510k is necessary for FDA regulatory approval. 

**Indications for Use:**
The algorithm is to aid clinician's in making informed decisions on patient diagnosis. The algorithm can be used in in-patient settings where a chest X-ray is requested. The algorithm is to be used in males and females between the ages of 20 and 70 years of age. 

**Device Limitations:**
The algorithm was trained on a relatively small sample size of 1431 postive Pneumonia cases. The race of individuals within the dataset is unknown. Any bias against racial groups cannot be estimated as a result. The majority of individuals fall within the age range of 20 - 70 years of age. There is not enough data for individuals outside of this age range to understand the algorithm's impact. The device may also require high compute power as compared to the average computer that a radiologist may use. 

**Clinical Impact of Performance:**
After training, the device is returns an F1 score of 0.53. The algorithm outperforms the average radiologist. The average radiologist scores 0.387. Not only will the model return a more accurate result, it will also reduce the amount of time needed to process an X-ray. 

### 2. Algorithm Design and Function

![Flowchart](./Images/Flowchart.png)

**DICOM Checking Steps:**
 1. Checks image type to verify that the image is an X-ray. 
 2. Checks patient position to verify that the view of the X-ray is either an antero-posterior view or postero-anterior view. 
 3. Checks the body part examined to verify that it is the chest being examined.  

**Preprocessing Steps:**
Each image will be rescaled by dividing 255. Each image will be normalized using the mean and standard deviation of the image. Each image will then be resized to fit the network at (1, 224, 224, 3). 

**CNN Architecture:**

![Output](./Images/Output.png)


### 3. Algorithm Training

**Parameters:**

* Types of augmentation used during training:
     - rescale=1./ 255.0
     - horizontal_flip = True
     - vertical_flip = False
     - height_shift_range= 0.1
     - width_shift_range=0.1
     - rotation_range=15
     - shear_range = 0.1
     - zoom_range=0.1
 
* Batch size: 100
* Optimizer learning rate = 0.0001
* Layers of pre-existing architecture that were frozen: First 17 Layers of VGG model
* Layers of pre-existing architecture that were fine-tuned: The last 3 layers of the VGG model 
* Layers added to pre-existing architecture: 11 Layers were added. These include - 
  1. Flatten()
  2. Dense(512, activation='relu')
  3. Dropout(0.2)
  4. Dense(256, activation='relu')
  5. Dropout(0.2)
  6. Dense(256, activation='relu')
  7. Dropout(0.2)
  8. Dense(128, activation='relu')
  9. Dropout(0.2)
  10 Dense(64, activation='relu')
  11. Dense(1, activation='sigmoid')
  
![layers](./Images/layers.png)


**Final Threshold and Explanation:**
The final threshold will be set at 0.62. This threshold corresponds to the highest F1 score. At this threshold, the F1 score is 0.53. This is relatively high as compared to CheXnet - a model created by Rajpurkar, et al. (2017). The model needs to be assessed on a larger dataset to verify the results. 

![ROC](./Images/ROC.png)

![history](./Images/history.png)

### 4. Databases
The database that was used contained 112 120 X-ray images from the NIH Chest X-ray Dataset. This dataset can be found at https://www.kaggle.com/nih-chest-xrays/data. The dataset is 45GB, and is considerably large. Among the X-ray images, only 1431 positive cases of Pneumonia. 

**Description of Training Dataset:** 
The training dataset is the first batch of dataset that the algorithm was trained on. 

**Description of Validation Dataset:** 
This is the second batch of data from the main dataset. This batch of data was used to assess the performance of the algorithm. 

### 5. Ground Truth
The ground truth was created using a natural language processing model to classify images. Medical reports were scanned and the accompanying diagnoses were used to label the images.


### 6. FDA Validation Plan

**Patient Population Description for FDA Validation Dataset:**
- The population is made up of male and females between the ages of 1 - 95 years old. The race of individuals is unknown. The diagnoses across the patient population included - Atelectasis, Cardiomegaly, Consolidation, Edema, Effusion, Emphysema, Fibrosis, Hernia, Infiltration, Mass, Nodule, Pleural thickening, Pneumonia, Pneumothorax. 

**Ground Truth Acquisition Methodology:**
The ground truth can be acquired by assessing the performance of radiologists on X-ray images when identifying positive cases of Pneumonia. It is important to note that patient history and clinical presentation cannot reported to the assessing radiologists. The assessment must be made on X-ray images alone as the algorithm ws presented with the same information and nothing more.  


**Algorithm Performance Standard:**
According to Rajpurkar, et al. (2017), the average performance of a radiologist is 0.387 on F1 scoring of a Chest X-ray. The CheXnet model was able to outperform the average radiologist with a score of 0.435. The model created here scored 0.53, which is higher than the standard performance. 

### References:

- NIH. (December 2017). NIH Chest X-rays. Retrieved 06 March 2022 from https://www.kaggle.com/nih-chest-xrays/data
- Rajpurkar, P., Irvin, J., Zhu, K. and Yang, B., 2017. CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays with Deep Learning. 3rd ed. Cornell University: arXiv.
