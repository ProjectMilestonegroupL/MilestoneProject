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
 
## Project structure

### Data

We also provide three CSV files [here](https://github.com/ProjectMilestonegroupL/MilestoneProject/blob/main/Milestone1/Data/csv_files_milestone1.zip): 


### Code

The notebooks `train_milestone1.ipynb` and `train_milestone1_alternative.ipynb` contains two complete training procedures.(remplacer par notre doc)

#### - architecture 1 with Pytorch `train_milestone1.ipynb`
 - imports
 - data recuperation
 - data reshape and transformation
 - neutral net
 - loss and optimizer
 - model training
 - model evaluation
 - .csv submission file generation

#### - architecture 2 with Keras `train_milestone1_alternative.ipynb`
 - imports
 - data recuperation
 - data reshape
 - model  
   - neutral net
   - loss & optimizer
   - .csv submission file generation
 - model training & evaluation
 
## Progression & improvements

To improve our regression, we had to take count to :
 - NN architecture (numbers of hidden layers & neurons)
 - activation function
 - optimizer
 - learning rate
 - number of epochs

 We created our regression model with our Pytorch knowledges.

 We reached quite early the minimum score required by implementing 3 hidden layers in our NN.
 We choose Adam as optimizer and ReLU as activation function.

 Then, we decided to try using Keras and we saw that it's easier and quicker to make our trainings.

# Milestone 2 : Tsunami induced building collapse detection

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/vita-epfl/introML-2021/blob/main/project/train.ipynb) (remplacer par notre doc)

## Dependencies
All required packages can be found in `requirements.txt`.

## Project structure

### Data

**You can find the dataset [here](https://drive.google.com/file/d/1otKxIvEP77Cap9VmUkujMrAMo4K8_F1c/view?usp=sharing).**

This project uses the fixed scale images from the [AIST Building Change Detection dataset](https://github.com/gistairc/ABCDdataset), which consists of pairs of pre- and post-tsunami aerial images. These images should be placed in a directory named `patch-pairs` inside the `data` directory.  
We also provide two CSV files [here](https://github.com/ProjectMilestonegroupL/MilestoneProject/blob/main/Milestone2/Data): 

- `train.csv` which contains the path to each image in the training set, as well as the target (0 for "surviving", 1 for "washed-away").
- `test.csv` which contains the path to each image in the test set.

### Code

The notebook `train_milestone2.ipynb` contains a complete training procedure.(remplacer par notre doc)

Here is the architecture of `train_milestone2.ipynb` (remplacer par notre doc)

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
- `dataset.py`: Contains `PatchPairsDataset`, a PyTorch Dataset class that loads pairs of images and their target, as well as a function to split datasets into training and validation sets.
- `evaluator.py`: Evaluates and generates prediction from a trained model
- `metrics.py`: Metrics to keep track of the loss and accuracy during training
- `trainer.py`: Contains `Trainer`, a class which implements the training loop as well as utilities to log the training process to TensorBoard, and load & save models
- `utils.py`: Utilities for displaying pairs of images and generating a submission CSV

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

You can run this notebook in Colab using the following link: https://colab.research.google.com/github/vita-epfl/introML-2021/blob/main/project/train.ipynb
(remplacer par notre doc)

**Important info:** 
- To train models much quicker, switch to a GPU runtime (*Runtime -> Change runtime type -> GPU*)
- Copy the Colab notebook to your Google Drive (*File -> Save a copy in Drive*) so that your changes to the training notebook persist.
- All files with the exception of the training notebook (`train.ipynb`) get deleted when your session terminates. Make sure to download all the relevant files (e.g. submissions, trained models, logs) before ending your session.


## Progression & improvements

To improve our regression, we had to take count to :
 - CNN architecture (convolution & maxpool layers) 
 - activation function
 - optimizer
 - learning rate
 - number of epochs
 
At first we based our architecture similarly at LeNet CNN and then we made several changes to obtain a good one. The final architecture is (insérer image du code)
We tried many optimizers and activation functions. 

Best configuration with Adam as optimizer and ReLU as activation function.

The model overfitted so we decided to try adding dropout or/and batch normalization. We obtained the best results with both simultaneously. 
We reached 0.959 validation accuracy with :
- dropout : 0.7
- batch normalization after the second convolutional layer

Here is the graph of validation loss & accuracy.
- in red : batch normalization 
- in orange : dropout
- in pink : batch normalization + dropout

<img src="https://github.com/ProjectMilestonegroupL/MilestoneProject/blob/main/Milestone2/Accuracy.png" width="400" height="400" />
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












