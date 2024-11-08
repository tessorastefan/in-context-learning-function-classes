# In-Context Learning with Transformers
This repository contains code and resources for exploring in-context learning using Transformer models.
The project focuses on how Transformers, like GPT-3, can learn to perform tasks from input-output examples provided in a prompt, without updating their internal parameters.
Specifically, we explore how a simplified Transformer can be trained to perform in-context learning on well-defined function classes, such as linear functions.

![image](https://github.com/user-attachments/assets/f80839a6-2c6e-4fa0-b51e-ed574b1b37a8)

## Overview
### Context
In this paper, the authors investigate in-context learning in large language models like GPT-3, where models adapt to new talks using examples in a prompt without updating their parameters. The central question is whether these models learn new tasks or simply recognize patterns from pre-training. To explore this, the paper shifts its focus to well-defined function classes, like linear functions or decision trees, rather than general natural language processing tasks, allowing for a more controlled analysis. This study positions in-context learning within the meta-learning paradigm, demonstrating that Transformers can encode algorithms that generalize to new tasks with minimal examples. The paper also examines how Transformer models scale to handle more complex tasks and higher-dimensional problems, contributing to broader AI research on adaptability, efficient learning, and how these models may outperform traditional methods in some cases.

## Problem
This paper investigates how large models like GPT-3 perform in-context learning, specifically whether they genuinely learn new tasks from prompts or simply recall pre-trained patterns. The authors focus on well-defined function classes, such as linear functions and decision trees, to analyze how models can generalize from examples. They also explore the models' robustness, testing their ability to handle out-of-distribution data, such as noisy inputs or shifted distributions. Lastly, the study examines how model size, problem complexity, and training data volume impact the effectiveness of in-context learning and the minimum data required for generalization.

## Approach
The authors focused on well-defined function classes (e.g., linear functions, decision trees) instead of general tasks to provide clearer insights into in-context learning. They trained Transformer models from scratch using input-output examples in prompts to see how well these models could predict outputs. The model's performance was compared to traditional algorithms like least squares, Lasso, and XGBoost to assess its in-context learning capabilities. The authors also tested the model's robustness by using out-of-distribution prompts, examining its ability to generalize to unseen data, especially under different input distributions. They found that larger models performed better with more complex, high-dimensional tasks, and the use of curriculum learning sped up training by gradually increasing task complexity, showing effective learning even with smaller training datasets.

## Discussion
### Curriculum Learning
Curriculum learning involves starting with simpler tasks and gradually increasing the difficulty as the model trains, which improves performance, especially on complex function classes. It was particularly helpful for higher-dimensional problems, where progress was slow without this structured approach. By gradually increasing complexity, the model learned more efficiently and reached better performance within the same training budget. This method also improved the model's ability to generalize and handle more challenging tasks during later stages of training. 
#### Question: How can curriculum learning be applied to NLP and computer vision tasks?
#### Answer: In NLP, curriculum learning could be used to first train a model on simple sentence structures or smaller vocabularies, gradually increasing complexity with longer sentences, ambiguous language, or multi-lingual text. In computer vision, curriculum learning could involve starting with clear, simple images and gradually introducing more challenging visuals.
### Out-of-Distribution Generalization
The paper examines out-of-distribution generalization in in-context learning, testing how models perform when faced with prompts that differ from their training distribution. The authors evaluated models on skewed inputs, noisy outputs, and inputs from different regions of the input space. Despite an increase in errors, the models still performed well, especially when model capacity was larger, indicating that they learned generalizable algorithms. This highlights the importance of ensuring model robustness in real-world scenarios, where data can shift unpredictably from training distributions.
#### Question: How can we improve the robustness and generalization of in-context learning models to handle distribution shifts, especially in real-world tasks?
#### Answer: To improve the robustness and generalization of in-context learning models to out-of-distribution data, strategies such as data augmentation, adversarial training, regularization, meta-learning, and model ensembling can be applied. Additionally, curriculum learning with gradual shifts in distribution can help models adapt more effectively to real-world variability and unpredictable data shifts.

## Analysis
### Architecture
This paper advances understanding of in-context learning by showing how large models, like Transformers, can adapt to new tasks at inference time using only example prompts, without parameter updates. By framing in-context learning as a form of meta-learning, it highlights a potential shift away from traditional fine-tuning toward more flexible, prompt-based adaptation. This work’s insights into scalability, curriculum learning, and robustness could influence future model design and training approaches across AI, promoting adaptable models that require less labeled data and task-specific tuning.
### Impact
This paper’s ideas intersect with Transformer architecture and training by examining how attention mechanisms and "induction heads" enable in-context learning from example prompts, allowing models to generalize without parameter updates. Curriculum learning is used to improve training, helping models handle increasingly complex tasks. The work suggests that in-context learning could replace traditional fine-tuning, enhancing adaptability and robustness, especially in real-world applications with distribution shifts.
### Further Developments
The authors could have further explored how Transformers encode algorithms for in-context learning, particularly focusing on internal mechanisms like "induction heads." A deeper analysis of model components, such as activation patterns and attention mechanisms, might offer insights into how the model selects relevant examples and generalizes. While the paper focuses on mathematical function classes, applying the model to more complex, real-world tasks remains underexplored and could expand its applicability. Additionally, comparing in-context learning models to meta-learning algorithms like MAML could provide a better understanding of their relative strengths and limitations in handling distribution shifts.

## Presentation Link

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

## Visualizations
The project includes two key visualizations:
* Training Loss Plot: Track the model's learning progress by plotting the loss over epochs.
* Predicted vs. True Output Plot: Compare the model's predictions against true outputs during inference to assess accuracy.

![training loss over epochs](https://github.com/user-attachments/assets/15e0effb-2632-43cb-a6c5-39256aa7219d)

## Resource Links
* Lecture by Gregory Valiant on the paper: https://www.youtube.com/watch?v=DiJsg93zQDc
* GitHub repository by Shivam Garg and Dimitris Tsipras on the paper: https://github.com/dtsip/in-context-learning
* More on curriculum learning: https://aclanthology.org/2023.ranlp-1.101/
* More on out-of-distribution generalization: https://arxiv.org/abs/2103.02667
* More on in-context learning: https://arxiv.org/abs/2211.15661
