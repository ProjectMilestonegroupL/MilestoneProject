# MilestoneProject
 Project introML group L
 AIcrowd team name : LU_EH_JD
 Best submission Milestone 1 : #140955
 Best submission Milestone 2 : #139964

graded

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
- Milestone 1 : Seismic collapse capacity prediction
- Milestone 2 : Tsunami induced building collapse detection

---

## Installation

You will also need to specify which libraries should be installed.

---

## Content

# Milestone 1 : Seismic collapse capacity prediction
 
## Project structure

### Data

**We provide three CSV files [here](https://github.com/ProjectMilestonegroupL/MilestoneProject/blob/main/Milestone1) into a zip.**

- `train_set.csv` & `val_set.csv` which contains metadata on ground motion intensity measures for about 14'000 past earthquakes recorded around the world.
- `test_set.csv` which contains metadata on ground motion intensity measures for 3'000 past earthquakes recorded around the world without their collapse capacity.

The following ground motion intensity measures are included in the dataset:
- spectral accelerations at 105 different periods ranging from 0.01s up to 10s : Sa(T)
- average spectral accelerations : Sa.avg
- two different measures of ground motion durations : da5_75 and da5_95
- filtered incremental velocity : FIV3 
- contain the collapse capacities : sat1_col (not in the test set)

### Code

The notebooks `train_milestone1.ipynb` and `train_milestone1_alternative.ipynb` contains two complete training procedures.

#### - architecture 1 with Pytorch `train_milestone1.ipynb`
 - imports
 - data recuperation
 - data reshape and transformation
 - neural network
 - loss and optimizer
 - model training
 - model evaluation
 - .csv submission file generation

#### - architecture 2 with Keras `train_milestone1_alternative.ipynb`
 - imports
 - data recuperation
 - data reshape
 - model  
   - neural network
   - loss & optimizer
   - .csv submission file generation
 - model training & evaluation
 
## Progression & improvements

We created our regression model with our Pytorch knowledges.

We reached quite early the minimum score required by implementing 2 hidden layers in our NN, with Adam as optimizer and ReLU as activation function.

Then, we decided to try using Keras and we saw that it's easier and quicker to make our trainings.

To improve our regression, we tried :
 - to modify the NN architecture (size and numbers of hidden layers)
 - different activation functions
   - reLU
   - seLU
   - sigmoid
   - softmax
   - softsign
 - different optimizers
   - adam
   - adamax
   - adagrad
   - adadelta
   - RMSprop
   - SGD
   - nadam
   - ftrl
 - adjust learning rate
   - learning rate decreasing at every epoch
   - learning rate decreasing strongly when validation loss start to increase
 - to adjust the number of epochs
 - to adjust the batch size
 - early stopping

Many possibilites gave us good results but we didn't find a configuration much better than others.
The best result found was with these forward NN architecture (AJOUTER IMAGE)

# Milestone 2 : Tsunami induced building collapse detection


## Dependencies
All required packages can be found in `requirements.txt`.

## Project structure

### Data

**You can find the dataset [here](https://drive.google.com/file/d/1otKxIvEP77Cap9VmUkujMrAMo4K8_F1c/view?usp=sharing).**

This project uses the fixed scale images from the [AIST Building Change Detection dataset](https://github.com/gistairc/ABCDdataset), which consists of pairs of pre- and post-tsunami aerial images. These images should be placed in a directory named `patch-pairs` inside the `data` directory.  
**We also provide two CSV files [here](https://github.com/ProjectMilestonegroupL/MilestoneProject/blob/main/Milestone2/Data/train_milestone2.ipynb):**

- `train.csv` which contains the path to each image in the training set, as well as the target (0 for "surviving", 1 for "washed-away").
- `test.csv` which contains the path to each image in the test set.

### Code

The notebook `train_milestone2.ipynb` contains a complete training procedure.
It contains everything needed to load the dataset, view image pairs, train a model and generate a CSV submission file with predictions.

You can open the notebook via Google Colab. [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ProjectMilestonegroupL/MilestoneProject/blob/main/Milestone2/train_milestone2.ipynb) 

Here is the architecture of `train_milestone2.ipynb` 

 - for Google Colab
 - setup
 - imports
 - device 
 - data
 - model 
   - network architecture (CNN)
   - loss, optimizer & scheduler
 - save, checkpoint and log
   - TensorBoard within notebook
 - model training
 - model evaluation
 - .csv submission file generation

In addition, here is a brief description of what each of the provided Python files does:
- `dataset.py`: contains `PatchPairsDataset`, a PyTorch Dataset class that loads pairs of images and their target, as well as a function to split datasets into training and validation sets.
- `evaluator.py`: evaluates and generates prediction from a trained model
- `metrics.py`: metrics to keep track of the loss and accuracy during training
- `trainer.py`: contains `Trainer`, a class which implements the training loop as well as utilities to log the training process to TensorBoard, and load & save models. Note : we changed this document by adding a scheduler.
- `utils.py`: utilities for displaying pairs of images and generating a submission CSV

If you are using Google Colab, keep in mind that any changes to files besides `train.ipynb` will get discarded when your session terminates.

### Experiment logging

By default, all runs are logged using [TensorBoard](https://www.tensorflow.org/tensorboard), which keeps track of the loss and accuracy. 
After installing TensorBoard, type
```
tensorboard --logdir=runs
```
in the terminal to launch it.

Alternatively, TensorBoard can be launched directly from notebooks, refer to `train_milestone2.ipynb` for more info. (remplacer par notre doc)

For more information on how to use TensorBoard with PyTorch, check out [the documentation](https://pytorch.org/docs/stable/tensorboard.html).

### Google Colab

You can run this notebook in Colab using the following link:(https://colab.research.google.com/github/ProjectMilestonegroupL/MilestoneProject/blob/main/Milestone2/train_milestone2.ipynb)


**Important info:** 
- To train models much quicker, switch to a GPU runtime (*Runtime -> Change runtime type -> GPU*)
- Copy the Colab notebook to your Google Drive (*File -> Save a copy in Drive*) so that your changes to the training notebook persist.
- All files with the exception of the training notebook (`train.ipynb`) get deleted when your session terminates. Make sure to download all the relevant files (e.g. submissions, trained models, logs) before ending your session.


## Progression & improvements

To improve our regression, we had to take count of :
 - CNN architecture  
 - activation function
 - optimizer
 - learning rate
 - number of epochs
 
At first we based our architecture similarly at LeNet CNN (2 convolutional layers and 2 maxpool layers) and we reached 0.929 accuracy.

Then we made several changes to obtain a good one. 
- We tried with 3 convolutional & 3 maxpool ; we obtained 0.935 accuracy.
- We tried to add a 4th maxpool just after the 3rd ; we reached 0.940 accuracy.

We tried to change optimizers and activation functions but still had best configuration with Adam as optimizer and reLU as activation function.

The model overfitted so we decided to try adding dropout or/and a batch normalization. 

Here is the graph of validation loss & accuracy.
- in red : with batch normalization 
- in orange : with dropout
- in pink : with batch normalization + dropout

<img src="https://github.com/ProjectMilestonegroupL/MilestoneProject/blob/main/Milestone2/Accuracy.png" width="400" height="400" />
We obtained the best results with both simultaneously. 


After that, we used a scheduler who decrease the learning rate when our model doesn't learn anymore.

We reached 0.959 validation accuracy with a 0.7 dropout just before the flatten and a batch normalization after the second convolutional layer.

Finally we tried to add a sigmoid layer, who is a popular activation function in CNN when it placed before the output, but it didn't provide us better results.

--- 
 
 ## Usage
 
The next section is usage, in which you instruct other people on how to use your project after they’ve installed it. This would also be a good place to include screenshots of your project in action.

---

 ## Contributing
 Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

 Please make sure to update tests as appropriate.

 --- 

 ## Authors
 Lucie Frésard, Edouard Heinkel and Jordan Dessibourg
 
 SCIPER : 316399, 301796, 287450

 ---

 ## License
 [EPFL](https://choosealicense.com/licenses/epfl/)












