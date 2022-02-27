# FDA  Submission

**Daniel da Cruz**

**Pneumonia Detection Algorithm**

## Algorithm Description 

### 1. General Information

**Intended Use Statement:** 
The Pneumonia Detection Algorithm is designed to detect the presence of pneumonia in X-ray radiographic imaging and assist clincians in diagnosing the aformentioned condition. The medical device falls under the Class II, and is considered a medium risk. The algorithm provides Computer-Assisted Diagnosis for clincians. An application for 510k is necessary for FDA regulatory approval. 

**Indications for Use:**
The algorithm is to aid clinician's in making informed decisions on patient diagnosis. The algorithm can be used in in-patient settings where a difficulty in breathing is a symptom. The algorithm is to be used in males and females between the ages of 20 and 70 years of age. 

**Device Limitations:**
The algorithm was trained on a relatively small sample size of 1430 postive Pneumonia cases. The race of individuals within the dataset is unknown. Any bias against racial groups cannot be estimated as a result. The majority of individuals fall within the age range of 20 - 70 years of age. There is not enough data for individuals outside of this age range to understand the algorithm's impact. 

**Clinical Impact of Performance:**
After training, the device is returns an F1 score of 0.39. 

### 2. Algorithm Design and Function

<< Insert Algorithm Flowchart >>

**DICOM Checking Steps:**

**Preprocessing Steps:**

**CNN Architecture:**


### 3. Algorithm Training

**Parameters:**
* Types of augmentation used during training
* Batch size
* Optimizer learning rate
* Layers of pre-existing architecture that were frozen
* Layers of pre-existing architecture that were fine-tuned
* Layers added to pre-existing architecture

<< Insert algorithm training performance visualization >> 

<< Insert P-R curve >>

**Final Threshold and Explanation:**

### 4. Databases
 (For the below, include visualizations as they are useful and relevant)

**Description of Training Dataset:** 



**Description of Validation Dataset:** 


### 5. Ground Truth



### 6. FDA Validation Plan

**Patient Population Description for FDA Validation Dataset:**

**Ground Truth Acquisition Methodology:**

**Algorithm Performance Standard:**
