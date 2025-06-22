<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Expense Category Classifier</title>
</head>
<body>

    <h1>Expense Category Classifier</h1>
    <p>This project presents a transformer-based model designed to classify business expenses into predefined categories based on textual descriptions and associated transaction details.</p>

    <h2>Overview</h2>
    <p>Accurately categorising expenses is crucial for financial tracking and analysis. This tool automates the process by taking a raw expense prompt and assigning it to a relevant expense category.</p>

    <h3>Example:</h3>
    <pre><code>=== Prompt ===
Uber | Private taxi for sharon | £89.00 | Mastercard | 2025-03-03

=== Predicted Category ===
Transportation
</code></pre>

    <h2>How it Works</h2>
    <p>The core of this classifier is a transformer model. It's trained on a dataset of expense records, learning to understand the patterns and relationships between the expense description, vendor, amount, payment method, and date, and its corresponding category.</p>
    <p>The model processes an input string containing all these details (e.g., "Uber | Private taxi for sharon | £89.00 | Mastercard | 2025-03-03") and outputs the most probable expense category (e.g., "Transportation").</p>

    <p><b>Note:</b> The training and data preparation steps were performed outside of the provided Colab notebook for efficiency and are not directly included in the public repository for this version.</p>

    <h2>Getting Started</h2>

    <h3>Prerequisites</h3>
    <p>To run or interact with the model's components (conceptually for training, or for future inference setup), you'll need the following:</p>
    <ul>
        <li>Python 3.x</li>
        <li><code>torch</code></li>
        <li><code>numpy</code></li>
        <li><code>pandas</code></li>
        <li><code>tiktoken</code></li>
    </ul>
    <p>You can install the necessary Python packages using pip:</p>
    <pre><code>pip install torch numpy pandas tiktoken</code></pre>

    <h3>Training (Conceptual)</h3>
    <p>The model was trained using a dataset of expense records, where each record consisted of a "prompt" (the expense details) and a "target" (the expense category). The training process involved:</p>
    <ul>
        <li><b>Data Preparation:</b> Transforming raw expense data into a format suitable for the model, including tokenisation and numerical encoding.</li>
        <li><b>Model Architecture:</b> A custom transformer model was built, incorporating self-attention mechanisms and feed-forward networks to learn complex relationships within the data.</li>
        <li><b>Training Loop:</b> Iteratively feeding the model training data, calculating the loss between predicted and actual categories, and updating the model's parameters using an optimiser. The model's performance was monitored on a separate validation set, and the best performing model checkpoint was saved.</li>
    </ul>

    <h3>Inference</h3>
    <p>While the training was conducted on a different environment, the trained model can be used for inference. An example of an inference output is provided above.</p>

    <h2>Next Steps</h2>
    <p>This expense classification model is currently undergoing further optimisation and refinement. We are actively working on improving its accuracy and efficiency. The goal is to productionise this model and make it accessible via an API for seamless integration into various financial applications. Future work will also involve exploring more advanced transformer architectures and potentially expanding the range of expense categories the model can identify.</p>

</body>
</html>
