# Cotton Plant Disease Classification Web Application :
This repository is about an end to end implementation of deep learning cotton plant disease classification web application using flask. 

## Dataset
The dataset is downloaded from ipcloud and has a total size of 4.2 GB. The dataset contains approximately 35,000 train images and 12,000 test images, organized into two folders. Each folder is divided into four classes: diseased cotton leaf (Fusarium Wilt), diseased cotton leaf (Leaf Curl Disease), fresh cotton leaf (Healthy Leaf), and diseased cotton leaf (Bacterial Blight Disease). Each image is in JPG format with a size of 256x256 pixels.

<img src="https://github.com/ShreeHarinesh1494/eveningdemo/blob/main/dataset.png" width=50% height=50%>

## Azure API
The Azure API is utilized to filter whether the image is a cotton leaf or not. If the image is identified as a cotton leaf, it is then processed by the model for classification into one of the four categories: Fusarium Wilt, Leaf Curl Disease, Healthy Leaf, or Bacterial Blight Disease.

## Data Set Preparation :
### Model Information:
Base Model: DenseNet121 with pre-trained weights from ImageNet.
Input Shape: (256, 256, 3)
Output: 4 classes (Healthy, Fusarium Wilt, Curl Virus, Bacterial Wilt)
Note: Azure API is used to filter non-leaf images.

## Dataset Preparation Steps:
### Dataset Structure:
Organize your dataset into directories for each category. The dataset should be divided into:

Training Set
Test Set

Each set should contain the following categories:

Healthy
Fusarium Wilt
Curl Virus
Bacterial Wilt

### Image Resizing:
All images should be resized to (256, 256, 3) to match the model’s input shape.

### Data Augmentation:
Apply data augmentation techniques to the training dataset to improve model generalization. Common techniques include rescaling, rotating, flipping, and zooming.

### Data Splitting:
Split the dataset into training, validation, and test sets. A common split is 80% for training, 10% for validation, and 10% for testing.


## DenseNet Model
Pretrained DenseNet121 model on ImageNet dataset is used. With the help of transfer learning, the last 8 layers of the model are tuned to solve the problem. The model is trained for 20 epoches and the accuracy is 95% on test data. 

<img src="https://i.imgur.com/O8ntGzS.png">

## Training Accuracy and Loss
<img src="https://github.com/ShreeHarinesh1494/eveningdemo/blob/main/graph.png">

## Confusion Matrix
<img src="https://github.com/myatmyintzuthin/Cotton-Plant-Disease-Classification-Web-Application/blob/main/assets/DenseNetConfusionMatrix.png" width=50% height=50%>

## Demo
<img src="https://github.com/myatmyintzuthin/Cotton-Plant-Disease-Classification-Web-Application/blob/main/assets/WebApplicationSample.png"  width=70% height=70%>

## Usage
- For model implementation and training, run [densenet121cottondisease.ipynb](https://github.com/Sakshi053/Cotton-Plant-Disease-Classification-Web-Application/blob/main/densenet121cottondisease.ipynb).
- You can also directly download [DenseNet121.h5](https://github.com/Sakshi053/Cotton-Plant-Disease-Classification-Web-Application/blob/main/DenseNet121.h5) without running the notebook.
- To run Flask app, run [app.py](https://github.com/Sakshi053/Cotton-Plant-Disease-Classification-Web-Application/blob/main/app.py).
- Make sure that you did not change any folder name in this repo.

## Cmds to run file
- Installing dependencies
```
pip install -r requirements.txt
```

- Model Training  
```
densenet121cottondisease.ipynb
```

- Inference

Model weight available at -  [DenseNet121.h5](https://github.com/Sakshi053/Cotton-Plant-Disease-Classification-Web-Application/blob/main/DenseNet121.h5) and store inside `/model` folder.

To run Flask, use:
```
python app.py
```

## Docker cmds
To build docker image, run:
```
docker build -t cotton .
```

Run docker image, using:
```
docker run --name cotton-app cotton
``` 

Stop docker, using:
```
docker stop cotton-app
```

## Credits
Thanks to my teammates [Myat Myint Zu Thin](https://github.com/myatmyintzuthin) and [Prachi Gupta](https://github.com/Prachigupta0305)
