# MilestoneProject
 Project introML

## Table of content
 1. [Description](#description)
 2. [Installation](#installation)
 3. [Content](#content)
 4. [Usage](#usage)
 5. [Contributing](#contributing)
 6. [Authors](#authors)
 7. [License](#license)

## Description
 This project is based on two milestones:
 1. Seismic collapse capacity prediction
 2. Tsunami induced building collapse detection

---

## Installation

---

## Content

 # Milestone 1 : Seismic collapse capacity prediction

 ### files 
 - train_set
 - val_set
 - test_set
 - milestone1.ipynb
 - milestone1alternative.ipynb
 
 
 ### code architecture 
 You are free to modify all of these Python files as desired for your experiments, although this is not necessary to achieve a very good performance in this challenge. If you are using Google Colab, keep in mind that any changes to files besides `train.ipynb` will get discarded when your session terminates.

 #### - architecture 1 with Pytorch (milestone1)
 - imports
 - data recuperation
 - data reshape and transformation
 - neutral net
 - loss and optimizer
 - model training
 - model evaluation
 - .csv submission file generation

 #### - architecture 2 with Keras (alternative milestone1)
 - imports
 - data recuperation
 - data reshape
 - model  
   - convolutional neutral net
   - loss & optimizer
   - .csv submission file generation
 - model training & evaluation
 
 ### progression and improvements

 #### parameters to improve our regression
 - NN architecture (numbers of hidden layers and neurons)
 - activation function
 - optimizer
 - learning rate

We created our regression model with our Pytorch knowledges.

We reached quite early the minimum score required by implementing 3 hidden layers in our NN.
We choose Adam as optimizer and ReLU as activation function.

Then, we decided to try using Keras and we saw that it's easier and quicker to make our trainings.


 # Milestone 2 : Tsunami induced building collapse detection


[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/vita-epfl/introML-2021/blob/main/project/train.ipynb)

## Dependencies
All required packages can be found in `requirements.txt`.

## Project structure

### Data

**You can find the dataset [here](https://drive.google.com/file/d/1otKxIvEP77Cap9VmUkujMrAMo4K8_F1c/view?usp=sharing).**

This project uses the fixed scale images from the [AIST Building Change Detection dataset](https://github.com/gistairc/ABCDdataset), which consists of pairs of pre- and post-tsunami aerial images. These images should be placed in a directory named `patch-pairs` inside the `data` directory.  
We also provide two CSV files:
- `train.csv` which contains the path to each image in the training set, as well as the target (0 for "surviving", 1 for "washed-away").
- `test.csv` which contains the path to each image in the test set.

### Code

The notebook `train.ipynb` contains a complete training procedure. 

In addition, here is a brief description of what each of the provided Python files does:
- `dataset.py`: Contains `PatchPairsDataset`, a PyTorch Dataset class that loads pairs of images and their target, as well as a function to split datasets into training and validation sets.
- `evaluator.py`: Evaluates and generates prediction from a trained model
- `metrics.py`: Metrics to keep track of the loss and accuracy during training
- `trainer.py`: Contains `Trainer`, a class which implements the training loop as well as utilities to log the training process to TensorBoard, and load & save models
- `utils.py`: Utilities for displaying pairs of images and generating a submission CSV

If you are using Google Colab, keep in mind that any changes to files besides `train.ipynb` will get discarded when your session terminates.

### Experiment logging

By default, all runs are logged using [TensorBoard](https://www.tensorflow.org/tensorboard), which keeps track of the loss and accuracy. 
After installing TensorBoard, type

### train code architecture 
 - for Google Colab
 - setup
 - imports
 - device 
 - data
 - model 
   - network architecture
   - loss, optimizer & scheduler
 - save, checkpoint and log
   - TensorBoard within notebook
 - model training
 - model evaluation
 - .csv submission file generation

 ### progression and improvements
 At first we based our architecture similarly at LeNet CNN and then we made several changes to obtain a good one.
 We tried many optimizers and activation functions. 

 Best configuration with Adam as optimizer and Sigmoid as activation functions.

--- 
 
 ## Usage
 
The next section is usage, in which you instruct other people on how to use your project after they’ve installed it. This would also be a good place to include screenshots of your project in action.

---

 ## Contributing
 Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

 Please make sure to update tests as appropriate.

 --- 

 ## Authors
 Lucie Fresard, Edouard Heinkel and Jordan Dessibourg

 ---

 ## License
 [EPFL](https://choosealicense.com/licenses/epfl/)













# Project code template

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/vita-epfl/introML-2021/blob/main/project/train.ipynb)

This is a PyTorch code template for milestone 2 of the project, which consists of identifying whether buildings have been washed away by a tsunami from aerial images.

This code contains everything needed to load the dataset, view image pairs, train a model and generate a CSV submission file with predictions.

## Dependencies
All required packages can be found in `requirements.txt`.

## Project structure

### Data

**You can find the dataset [here](https://drive.google.com/file/d/1otKxIvEP77Cap9VmUkujMrAMo4K8_F1c/view?usp=sharing).**

This project uses the fixed scale images from the [AIST Building Change Detection dataset](https://github.com/gistairc/ABCDdataset), which consists of pairs of pre- and post-tsunami aerial images. These images should be placed in a directory named `patch-pairs` inside the `data` directory.  
We also provide two CSV files:
- `train.csv` which contains the path to each image in the training set, as well as the target (0 for "surviving", 1 for "washed-away").
- `test.csv` which contains the path to each image in the test set.

### Code

The notebook `train.ipynb` contains a complete training procedure. Feel free to modify it as desired to improve the performance of your model.


In addition, here is a brief description of what each of the provided Python files does:
- `dataset.py`: Contains `PatchPairsDataset`, a PyTorch Dataset class that loads pairs of images and their target, as well as a function to split datasets into training and validation sets.
- `evaluator.py`: Evaluates and generates prediction from a trained model
- `metrics.py`: Metrics to keep track of the loss and accuracy during training
- `trainer.py`: Contains `Trainer`, a class which implements the training loop as well as utilities to log the training process to TensorBoard, and load & save models
- `utils.py`: Utilities for displaying pairs of images and generating a submission CSV

You are free to modify all of these Python files as desired for your experiments, although this is not necessary to achieve a very good performance in this challenge. If you are using Google Colab, keep in mind that any changes to files besides `train.ipynb` will get discarded when your session terminates.

## Experiment logging
By default, all runs are logged using [TensorBoard](https://www.tensorflow.org/tensorboard), which keeps track of the loss and accuracy. 
After installing TensorBoard, type
```
tensorboard --logdir=runs
```
in the terminal to launch it.

Alternatively, TensorBoard can be launched directly from notebooks, refer to `train.ipynb` for more info.

For more information on how to use TensorBoard with PyTorch, check out [the documentation](https://pytorch.org/docs/stable/tensorboard.html).

## Google Colab

You can run this notebook in Colab using the following link: https://colab.research.google.com/github/vita-epfl/introML-2021/blob/main/project/train.ipynb

**Important info:** 
- To train models much quicker, switch to a GPU runtime (*Runtime -> Change runtime type -> GPU*)
- Copy the Colab notebook to your Google Drive (*File -> Save a copy in Drive*) so that your changes to the training notebook persist.
- All files with the exception of the training notebook (`train.ipynb`) get deleted when your session terminates. Make sure to download all the relevant files (e.g. submissions, trained models, logs) before ending your session.

