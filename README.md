##                                         狗狗分类器项目

### 项目预览

这是一个优达学城的狗狗分类器项目，目的是分步骤地设计一个狗狗分类器，使其在任何时候输入一副图像，都能分辨出是不是狗狗，并输出狗狗的种类（有133个狗狗品种）。有趣的是，如果输入一个人类的照片，这个分类器可以辨识出这个人和哪个品种的狗狗相似呢！

在这个项目中，我们主要是使用深度学习模型（Deep CNN）来搭建算法，并且会应用迁移学习来提高算法的效率。在算法设计过程中，我们会从最简单的模型开始搭建，逐渐提高算法的复杂度，来提高预测的准确性。

![image](https://github.com/YapingZ/Dog_classification/blob/main/doginpanic.jpeg)

### 项目思路

1. 导入数据集（狗狗数据集和人脸数据集），并将其分为训练数据，校验数据和测试数据。使用dog_names字符串格式的狗狗品种名称列表，用于标识标签。

2. 使用 OpenCV 实现的 [Haar 特征级联分类器（Haar feature-based cascade classifiers）](http://docs.opencv.org/trunk/d7/d8b/tutorial_py_face_detection.html) 来检测图片中的人脸数据集中的人脸。

3. 用CNN从头搭建狗狗分类器：我们使用Keras自己搭建，使用了卷积层、非线性、池化层以及dropout等，但分类效果不好，准确率只有3.11%。这个结果比随机猜测还是有改进的，但离真正的预测要求还差很远。

4. 使用Transfer learning（迁移学习）的方法搭建狗狗分类器：迁移学习是就是把已经训练好的模型参数迁移到新的模型来帮助新模型训练的方法，可以在极大提高模型性能的情况下减少训练时间。我们选用了Resnet50作为预训练模型，训练的准确率达到了81.6%，基本达到了可接受的性能。

5. 综合设计分类器：将人类检测算法和小狗分类算法综合起来，以达到输入任意图片，判断图片中是否含有人、小狗或者两者都没有的效果。如果检测到了小狗，模型将进一步输出小狗的种类，如果检测到人脸，将会把与人脸最匹配的小狗品种输出来，否则会输出错误信息。

 

### 依赖库

要想顺利运行程序，需要的依赖库包括以下几个：

opencv-python==3.2.0.6
h5py==2.6.0
matplotlib==2.0.0
numpy==1.12.0
scipy==0.18.1
tqdm==4.11.2
keras==2.0.2
scikit-learn==0.18.1
pillow==4.0.0
ipykernel==4.6.1
tensorflow-gpu==1.0.0

### 项目运行指南

###### 如果想要完整运行该程序，你需要自己下载一些数据和与训练模型，具体为：

1. Clone the repository and navigate to the downloaded folder.
```	
git clone https://github.com/udacity/dog-project.git
cd dog-project
```

2. Download the [dog dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/dogImages`. 
3. Download the [human dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/lfw.zip).  Unzip the folder and place it in the repo, at location `path/to/dog-project/lfw`.  If you are using a Windows machine, you are encouraged to use [7zip](http://www.7-zip.org/) to extract the folder. 
4. Donwload the [VGG-16 bottleneck features](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/DogVGG16Data.npz) for the dog dataset.  Place it in the repo, at location `path/to/dog-project/bottleneck_features`.
5. Open the notebook.
```
jupyter notebook dog_app.ipynb
```

### 文件描述

本项目中包含的文件及文件夹:
1. haarcascades
    - haarcascade_frontalface_alt.xml:  由OpenCV提供的人脸检测的预训练模型
2. requirements :所需要的安装包详情
3. saved_models
    - weights.best.Resnet50.hdf5: 在最佳校验loss下保存的Resnet50模型权重
    - weights.best. VGG16.hdf5: 在最佳校验loss下保存的VGG16模型权重
4. test images:6副随机测试图片
5. dog_app-zh.ipynb: jupyter notebook文件， 狗狗分类器模型 
6. dog_app-zh.html: html文件， 狗狗分类器模型 
7. extract_bottleneck_features.py: 给定图像的 bottleneck features 
8. Report.pdf 项目报告

Note: 
The dog image dataset used by this project can be downloaded here: https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip
The human image dataset can be downloaded here: https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/lfw.zip

### 致谢

感谢优达学城提供的项目题材及相关数据集。