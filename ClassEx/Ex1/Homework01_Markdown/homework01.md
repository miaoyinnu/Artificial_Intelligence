# Homework01

# 1.目录

---

- [Homework01](#homework01)
- [1.目录](#1目录)
- [2.文件初始化](#2文件初始化)
  - [2.1切换并创建文件夹](#21切换并创建文件夹)
  - [2.2从Tronclass下载源代码并到课程文件夹](#22从tronclass下载源代码并到课程文件夹)
  - [2.3在本地创建Git仓库,并在Github创建**Artificial\_Intelligence** repositories](#23在本地创建git仓库并在github创建artificial_intelligence-repositories)
  - [2.4在Github页面可以看见刚创建的仓库(https://github.com/miaoyinnu/Artificial\_Intelligence)](#24在github页面可以看见刚创建的仓库httpsgithubcommiaoyinnuartificial_intelligence)
- [3.项目环境搭建](#3项目环境搭建)
  - [3.1打开Jupyter Notebook](#31打开jupyter-notebook)
  - [3.2安装必要的package](#32安装必要的package)
  - [3.3在Jupyter notebooks打开课程文件](#33在jupyter-notebooks打开课程文件)
- [4.运行文件](#4运行文件)
  - [4.1\*\*`ModuleNotFoundError**: No module named 'cnn_utils'`运行报错](#41modulenotfounderror-no-module-named-cnn_utils运行报错)
  - [4.2\*\*`AttributeError**: module 'tensorflow.compat.v1' has no attribute 'contrib'`报错](#42attributeerror-module-tensorflowcompatv1-has-no-attribute-contrib报错)


# 2.文件初始化

---

## 2.1切换并创建文件夹

```bash
cd course/Artificial_Intelligence
mkdir ClassEx
cd ClassEx
mkdir Ex1

```

## 2.2从Tronclass下载源代码并到课程文件夹

```bash
mv /mnt/c/Users/Lk9/Downloads/01_搭建卷积神经网络以及应用.ipynb/mnt/c/course/Artificial_Intelligence/ClassEx/Ex1
```

## 2.3在本地创建Git仓库,并在Github创建**Artificial_Intelligence** repositories

```bash
cd course/Artificial_Intelligence
git init
git add .
git commit
git remote add origin https://github.com/miaoyinnu/Advanced_Programming
git merge origin/main --allow-unrelated-histories
```

## 2.4在Github页面可以看见刚创建的仓库([https://github.com/miaoyinnu/Artificial_Intelligence](https://github.com/miaoyinnu/Artificial_Intelligence))

![image.png](image.png)

---

# 3.项目环境搭建

---

## 3.1打开Jupyter Notebook

![image.png](image%201.png)

## 3.2安装必要的package

```bash
pip install h5py
pip install tensorflow
```

## 3.3在Jupyter notebooks打开课程文件

![image.png](image%202.png)

---

# 4.运行文件

---

## 4.1**`ModuleNotFoundError**: No module named 'cnn_utils'`运行报错

![image.png](image%203.png)

- 代码出现报错**`ModuleNotFoundError**: No module named 'cnn_utils'`
- 从互联网下载`cnn_utils` ,
- 并下载`cnn_utils`里的数据集文件 `test_signs.h5`  `train_signs.h5`

```bash
mkdir datasets ##创建数据集文件夹
```

- 将数据集文件 `test_signs.h5`  `train_signs.h5`放在数据集文件夹
- 运行成功

![image.png](image%204.png)

## 4.2**`AttributeError**: module 'tensorflow.compat.v1' has no attribute 'contrib'`报错

![image.png](image%205.png)

- 经发现安装的tensorrflow版本2,课程源代码使用版本是1。原因是TensorFlow 2.x之后把contrib这个库取消了
- 创建一个新的 Conda 虚拟环境，并在其中尝试安装 TensorFlow 1.15及其所需package

```bash
conda create -n tf_env python=3.7
conda activate tf_env
conda install tensorflow=1.15
pip install h5py
pip install matplotlib
pip install scipy

```

- 安装ipykernel包,可以将虚拟环境作为 Jupyter 内核添加到 Jupyter Notebook 中。

```bash
pip install ipykernel
python -m ipykernel install --user --name=tf_env --display-name "Python (tf_env)"
```

- 在Jupyter Notebook中切换虚拟环境tf_env

![image.png](image%206.png)

- 依次运行代码,得出结果

![image.png](image%207.png)

- Git提交,同步修改

![image.png](image%208.png)

- Github仓库同步看到修改

([https://github.com/miaoyinnu/Artificial_Intelligence/tree/master/ClassEx/Ex1](https://github.com/miaoyinnu/Artificial_Intelligence/tree/master/ClassEx/Ex1))

![image.png](image%209.png)

---