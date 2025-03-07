# Breast Cancer Image Classification with DenseNet121

### I. Overview
This repository focuses on a project dedicated to classifying **Breast Ultrasound Images** into three categories: 
- **benign**
- **malignant**
- **normal**

The classification model used in this project relies on deep learning techniques, particularly **Convolutional Neural Networks (CNN)** and **Transfer Learning**, harnessing the power of a base model called **DenseNet121**. It is trained on a comprehensive dataset of annotated breast ultrasound images, leveraging these deep learning approaches to enhance its performance.

Transfer learning involves adapting a pre-trained model to a specific task by fine-tuning it with a smaller, task-specific dataset. Here, the initial layers of DenseNet121, having acquired general features from a diverse dataset, remain frozen. Subsequent layers, responsible for learning task-specific details, are adjusted to better align with the specific characteristics of breast ultrasound image classification. 

----------------------

### II. Dataset
![image](https://github.com/m3mentomor1/Breast-Cancer-Image-Classification-with-DenseNet121/assets/95956735/47e76b23-1542-4576-9127-6f30077733f3)

#### Breast Ultrasound Images
- Breast cancer is one of the most common causes of death among women worldwide. Early detection helps in reducing the number of early deaths. The data reviews the medical images of breast cancer using ultrasound scan. Breast Ultrasound Dataset is categorized into three classes: normal, benign, and malignant images. Breast ultrasound images can produce great results in classification, detection, and segmentation of breast cancer when combined with machine learning.
- The data collected at baseline include breast ultrasound images among women in ages between 25 and 75 years old. This data was collected in 2018. The number of patients is 600 female patients. The dataset consists of 780 images with an average image size of 500*500 pixels. The images are in PNG format. The ground truth images are presented with original images. The images are categorized into three classes, which are normal, benign, and malignant.

**Source:** Al-Dhabyani W, Gomaa M, Khaled H, Fahmy A. Dataset of breast ultrasound images. Data in Brief. 2020 Feb;28:104863. DOI: 10.1016/j.dib.2019.104863.

**Download Dataset Here:** https://www.kaggle.com/datasets/aryashah2k/breast-ultrasound-images-dataset

----------------------

### III. Type of Learning Used
#### Supervised Learning
- a type of learning in machine learning that involves training an algorithm on labeled data, where input samples are paired with corresponding output labels. The objective is to learn a mapping from input data to correct output labels by adjusting internal parameters during training, minimizing the difference between predicted outputs and true labels.

----------------------

### IV. Model Algorithm
#### Neural Networks 
- a class of algorithms inspired by the structure and functioning of the human brain. It consists of interconnected nodes organized into layers. These layers typically include an input layer, one or more hidden layers, and an output layer. Each connection between nodes has an associated weight, and nodes within a layer may have activation functions.

----------------------

### V. Model Architecture 
#### Convolutional Neural Network (CNN)
- a type of deep learning model architecture designed specifically for processing structured grid data, such as images. CNNs have proven to be highly effective in computer vision tasks, including image classification, object detection, segmentation, and more. They are characterized by their ability to automatically and adaptively learn spatial hierarchies of features directly from the data.
##
The model's architecture is implemented using the **Keras Sequential API**. Below is a detailed summary of its layers:

1. **DenseNet121 Base Model (Functional):**
   - Output Shape: (None, 8, 8, 1024)
   - Parameters: 7,037,504

2. **Flatten Layer:**
   - Output Shape: (None, 65536)

3. **Dense Layer 1:**
   - Output Shape: (None, 1024)
   - Activation Function: ReLU (Rectified Linear Unit)
   - Parameters: 67,109,888

4. **Dropout Layer 1:**
   - Rate: 0.5

5. **Dense Layer 2:**
   - Output Shape: (None, 1024)
   - Activation Function: ReLU (Rectified Linear Unit)
   - Parameters: 1,049,600

6. **Dropout Layer 2:**
   - Rate: 0.3

7. **Dense Layer 3:**
   - Output Shape: (None, 512)
   - Activation Function: ReLU (Rectified Linear Unit)
   - Parameters: 524,800

8. **Dense Layer 4:**
   - Output Shape: (None, 128)
   - Activation Function: ReLU (Rectified Linear Unit)
   - Parameters: 65,664

9. **Dense Output Layer:**
   - Output Shape: (None, 3)
   - Activation Function: Softmax
   - Parameters: 387

**Total Trainable Parameters:** 68,750,339 (262.26 MB)  
- These are the parameters that the model learns and adjusts during the training process. They include the weights and biases in the dense and fully connected layers. The number **68,750,339** represents the total count of trainable parameters, and the value **262.26 MB** is an approximation of the memory required to store these parameters.

**Total Non-trainable Parameters:** 7,037,504 (26.85 MB)
- These are the parameters that are not updated during training. In this case, they likely correspond to the weights of the pre-trained DenseNet121 base model. The number **7,037,504** represents the total count of non-trainable parameters, and the value **26.85 MB** is an approximation of the memory required to store these parameters.

----------------------

### VI. Base Model
#### DenseNet121
- a CNN architecture widely used as a base model for image classification tasks. It is part of the DenseNet (Densely Connected Convolutional Networks) family of models. These architectures are characterized by dense connectivity patterns, where each layer receives direct input from all preceding layers. The "121" in DenseNet121 denotes the total number of layers in the network.

**Download Weights File Here:** https://storage.googleapis.com/tensorflow/keras-applications/densenet/densenet121_weights_tf_dim_ordering_tf_kernels_notop.h5

----------------------

### VII. Dependencies

***Main***
- **Pandas** - a data analysis library that provides data structures like DataFrames for efficient data handling. 
- **NumPy** - a library for scientific computing with Python.
- **Matplotlib** - a comprehensive library for creating static, interactive, and animated plots in Python, facilitating data visualization tasks.
- **Seaborn**
- **Pillow**
- **TensorFlow**
- **Keras** - a high-level neural networks API written in Python, capable of running on top of TensorFlow. This library is utilized for building and training deep learning models.
- **scikit-learn**

***Others***
- **h5py**
- **Requests**
- **Streamlit**

**TXT File:** [requirements.txt](https://github.com/m3mentomor1/Breast-Cancer-Image-Classification-with-DenseNet121/blob/f8a7a3b747ab8b3d81acb7bbda0251ff1063ee14/requirements.txt)

----------------------

### VIII. Model Evaluation
| Set          | Loss      | Accuracy  |
|--------------|-----------|-----------|
| Train        | 0.038702  | 99.04%    |
| Validation   | 0.188313  | 90.97%    |
| Test         | 0.136501  | 94.94%    |

After evaluating the model using the test set ([test_images](https://github.com/m3mentomor1/Breast-Cancer-Image-Classification-with-DenseNet121/tree/7eb700a208efcd84beafbf412274f594bf1b85ce/test_images)), it demonstrated an overall accuracy of "**94.94%**". (For reference see: )

**Download Model Here:**
- Single File: [model.h5](https://drive.google.com/file/d/1lxY2mH7dQ9hVh5mYipKWLCBuKJRDD1sj/view?usp=drive_link)
- Splitted File: [splitted_model](https://github.com/m3mentomor1/Breast-Cancer-Image-Classification-with-DenseNet121/tree/fcb1bcfedd11d733427bd96ae791ed0fbeefdcd5/splitted_model) (Splitted using [PineTools File Splitter](https://pinetools.com/split-files))

----------------------

### IX. Deployment
<img src="https://github.com/m3mentomor1/Breast-Cancer-Image-Classification-with-DenseNet121/assets/95956735/6d0001fd-6890-44aa-8f25-223b21e8ab39" width="300" />

- a free and open-source Python framework to rapidly build and share beautiful machine learning and data science web apps. 
##
The model is deployed using **Streamlit**, allowing for a straightforward and accessible user interface where users can conveniently do breast cancer image classification.

**Access the app here:** https://breast-cancer-image-classification-with-densenet121-v9dybugp4h.streamlit.app/
