# AI Translator

Welcome to the AI Translator Project! This project is designed to leverage advanced machine learning techniques for language translation and other natural language processing tasks. The repository contains multiple Jupyter notebooks covering various aspects of the project, created and trained on Google Colab.

This project was made as course work for the CS5100 Foundations of Artificial Intelligence course at Northeastern University.

## Table of Contents

- [Model and Training](#model-and-training)
- [Datasets](#datasets)
- [Usage](#usage)
- [Collaborators](#collaborators)
- [Contributing](#contributing)

## Model and Training

### Model
The model architecture for this experiment is T5 (Text-To-Text Transfer Transformer). Specifically, the 't5-small' variant was utilized due to its balance between model size and computational efficiency. T5 is renowned for its versatility across various natural language processing tasks, making it an optimal choice for conditional text generation, such as translation. The model training code can be found in the [t5-model-trainer.ipynb](/t5-model-trainer.ipynb) file.

### Optimizer
The AdamW optimizer was chosen for parameter optimization during training. AdamW extends the Adam optimizer by incorporating weight decay regularization, which penalizes large weights to prevent overfitting. This choice was made to balance the benefits of adaptive learning rates with the regularization capabilities of weight decay.

### Learning rate
A learning rate of 0.0001 was selected for the optimizer. The learning rate determines the step size during optimization and plays a crucial role in controlling the convergence speed and stability of the training process. The chosen learning rate was determined through empirical experimentation and common practices in training transformer-based models.

### Training
The training loop ran for 3 epochs, iterating over batches of training data. Each batch consisted of source language texts (lang1_texts) and their corresponding target language texts (lang2_texts), obtained from a dataset. The model was trained for conditional text generation, with inputs fed along with attention masks and labels for computing the loss. Explicit memory management was performed to handle memory efficiently during training.

## Datasets
Our initial intention was to use languages that uncommon on the global scale, such as regional languages in India. However, due to lack of comprehensive data and computing resources, we were unable to train the model on such languages. Thus we trained the model on three language pairs; English to German, Spanish, French and vice-versa. The datasets were obtained from [Opus Corpora](https://opus.nlpl.eu/).

## Usage
The application has a [UI interface](https://github.com/srinivasa-sameer/ai-doc-translator) that was made using React. Users can use this interface to translate text or PDF documents.

The UI application hits the backend which is exposed in [backend.ipynb](backend.ipynb). The code in this file utilizes the saved model based on the input languages and output language required, translates the text or PDF, and sends the response back to the UI applicaion.

## Collaborators
Collaborators on this project-
- Gibran Myageri
- Srinivas Sameer Addepalli
- Srikar Nallapu
- Varsha Ramesh

## Contributing
We welcome any contributions to this project!