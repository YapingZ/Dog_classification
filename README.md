##                                         狗狗分类器项目

### 项目预览

这是一个优达学城的狗狗分类器项目，目的是分步骤地设计一个狗狗分类器，使其在任何时候输入一副图像，都能分辨出是不是狗狗，并输出狗狗的种类（有133个狗狗品种）。有趣的是，如果输入一个人类的照片，这个分类器可以辨识出这个人和哪个品种的狗狗相似呢！

在这个项目中，我们主要是使用深度学习模型（Deep CNN）来搭建算法，并且会应用迁移学习来提高算法的效率。在算法设计过程中，我们会从最简单的模型开始搭建，逐渐提高算法的复杂度，来提高预测的准确性。

![image](https://github.com/YapingZ/Dog_classification/blob/main/doginpanic.jpeg)

## 项目指南

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

