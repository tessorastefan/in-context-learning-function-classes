# In-Context Learning with Transformers
This repository contains code and resources for exploring in-conext learning using Transformer models.
The project focuses on how Transformers, like GPT-3, can learn to perform tasks from input-output examples provided in a prompt, without updating their internal parameters.
Specifically, we explore how a simplified Transformer can be trained to perform in-context learning on well-defined function classes, such as linear functions.

## Project Overview
This project demonstrates how a Transformer model can be trained from scratch to:
* Predict outputs for linear functions based on input-output examples provided in a prompt.
* Generalize to unseen queries and handle out-of-distribution scenarios.
* Apply curriculum learning to gradually increase the complexity of function classes, improving training efficiency.

## Key Features
* Transformer Model: A simplified Transformer encoder is used for predicting scalar outputs from input-output pairs.
* Function Classes: Focus on well-defined mathematical function classes.
* In-Context Learning: The model adapts to new tasks at inference time without parameter updates, relying only on the examples in the prompt.
* Robustness Testing: Tests the model’s ability to generalize to out-of-distribution inputs.
* Visualization: Includes visualizations of training loss and predicted vs. true outputs to evaluate model performance.

## How It Works
The Transformer model in this project is designed to:
1. Train on a set of input-output pairs derived from a mathematical function class.
2. Learn from these pairs to predict outputs for unseen queries based on the examples in the prompt.
3. Generalize to out-of-distribution inputs and handle different data conditions.

## Curriculum Learning
To help the model learn more efficiently, curriculum learning is applied. The training starts with simpler tasks and progressively increases in difficulty, allowing the model to improve faster and handle more complex data.

## Inference
During inference, the model is tested on new tasks where it uses only the examples in the prompt (in-context examples) to predict the output of a query. The model is never updated during inference, showcasing its ability to adapt to unseen data based solely on the prompt.

## Visualizations
The project includes two key visualizations:
* Training Loss Plot: Track the model's learning progress by plotting the loss over epochs.
* Predicted vs. True Output Plot: Compare the model's predictions against true outputs during inference to assess accuracy.

## Resource Links
* Lecture by Gregory Valiant on the paper: https://www.youtube.com/watch?v=DiJsg93zQDc
* GitHub repository by Shivam Garg and Dimitris Tsipras on the paper: https://github.com/dtsip/in-context-learning
* More on curriculum learning: https://aclanthology.org/2023.ranlp-1.101/
* More on out-of-distribution generalization: https://arxiv.org/abs/2103.02667
* More on in-context learning: https://arxiv.org/abs/2211.15661
