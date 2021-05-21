# MilestoneProject
Project introML

# Table of content
1. [Description](#description)
2. [Installation](#installation)
3. [Content](#content)
4. [Usage](#usage)
5. [Contributing](#content)
6. [Authors](#authors)
7. [License](#license)



## Description
This project is based on two milestones:
1. Seismic collapse capacity prediction
2. Tsunami induced building collapse detection

---

## Installation

---

## Usage

The next section is usage, in which you instruct other people on how to use your project after they’ve installed it. This would also be a good place to include screenshots of your project in action.

## Content

# Milestone 1 : Seismic collapse capacity prediction

### files 
- train_set
- val_set
- test_set
- milestone1.ipynb
- milestone1alternative.ipynb

### code architecture 

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

### files 
- milestone2train.ipynb
- ..

### code architecture 
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

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

--- 

## Authors
Lucie Fresard, Edouard Heinkel and Jordan Dessibourg

---

## License
[EPFL](https://choosealicense.com/licenses/epfl/)
