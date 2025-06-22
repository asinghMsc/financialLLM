# Expense Category Classifier

This project presents a transformer-based model designed to classify business expenses into predefined categories based on textual descriptions and associated transaction details.

## Overview

Accurately categorising expenses is crucial for financial tracking and analysis. This tool automates the process by taking a raw expense prompt and assigning it to a relevant expense category.

### Example:

=== Prompt === <br>
Uber | Private taxi for sharon | £89.00 | Mastercard | 2025-03-03

=== Predicted Category === <br>
Transportation


## How it Works

The core of this classifier is a transformer model. It's trained on a dataset of expense records, learning to understand the patterns and relationships between the expense description, vendor, amount, payment method, and date, and its corresponding category.

The model processes an input string containing all these details (e.g., "Uber | Private taxi for sharon | £89.00 | Mastercard | 2025-03-03") and outputs the most probable expense category (e.g., "Transportation").

(Note: The training and data preparation steps were performed outside of the provided Colab notebook for efficiency and are not directly included in the public repository for this version.)


Training (Conceptual) <br>
The model was trained using a dataset of expense records, where each record consisted of a "prompt" (the expense details) and a "target" (the expense category). The training process involved<br>

Data Preparation: <br>
Transforming raw expense data into a format suitable for the model, including tokenisation and numerical encoding.<br>
Model Architecture: A custom transformer model was built, incorporating self-attention mechanisms and feed-forward networks to learn complex relationships within the data.<br>

Training Loop: <br>
Iteratively feeding the model training data, calculating the loss between predicted and actual categories, and updating the model's parameters using an optimiser. The model's performance was monitored on a separate validation set, and the best performing model checkpoint was saved.<br>

Inference <br>
While the training was conducted on a different environment, the trained model can be used for inference. An example of an inference output is provided above.

Next Steps <br>
This expense classification model is currently undergoing further optimisation and refinement. We are actively working on improving its accuracy and efficiency. The goal is to productionise this model and make it accessible via an API for seamless integration into various financial applications. Future work will also involve exploring more advanced transformer architectures and potentially expanding the range of expense categories the model can identify.
