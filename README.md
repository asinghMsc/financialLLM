<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Expense Category Classifier</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            color: #333;
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f6f8fa; /* GitHub-like background */
        }
        h1, h2, h3 {
            color: #000000;
            border-bottom: 1px solid #eaecef; /* Subtle line like GitHub */
            padding-bottom: 10px;
            margin-top: 30px;
        }
        h1 {
            font-size: 2em;
        }
        h2 {
            font-size: 1.5em;
        }
        h3 {
            font-size: 1.2em;
        }
        code {
            font-family: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, Courier, monospace;
            background-color: #f3f4f6;
            padding: 0.2em 0.4em;
            border-radius: 6px;
            color: #000000;
        }
        pre {
            background-color: #eef0f2; /* Lighter background for code blocks */
            padding: 16px;
            border-radius: 6px;
            overflow-x: auto;
            font-family: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, Courier, monospace;
            line-height: 1.45;
            color: #000000;
        }
        ul {
            padding-left: 20px;
        }
        li {
            margin-bottom: 8px;
        }
        .note {
            background-color: #fff9e6; /* Light yellow for notes */
            border-left: 4px solid #ffc107; /* Yellow border */
            padding: 10px 15px;
            margin: 20px 0;
            border-radius: 4px;
        }
    </style>
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

    <div class="note">
        <strong>Note:</strong> The training and data preparation steps were performed outside of the provided Colab notebook for efficiency and are not directly included in the public repository for this version.
    </div>

    <h2>Getting Started</h2>

    <h3>Prerequisites</h3>
    <p>To run or interact with the model's components (conceptually for training, or for future inference setup), you'll need the following:</p>
    <ul>
        <li><code>Python 3.x</code></li>
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
        <li><strong>Data Preparation:</strong> Transforming raw expense data into a format suitable for the model, including tokenisation and numerical encoding.</li>
        <li><strong>Model Architecture:</strong> A custom transformer model was built, incorporating self-attention mechanisms and feed-forward networks to learn complex relationships within the data.</li>
        <li><strong>Training Loop:</strong> Iteratively feeding the model training data, calculating the loss between predicted and actual categories, and updating the model's parameters using an optimiser. The model's performance was monitored on a separate validation set, and the best performing model checkpoint was saved.</li>
    </ul>

    <h3>Inference</h3>
    <p>While the training was conducted on a different environment, the trained model can be used for inference. An example of an inference output is provided above.</p>

    <h2>Next Steps</h2>
    <p>This expense classification model is currently undergoing further optimisation and refinement. We are actively working on improving its accuracy and efficiency. The goal is to productionise this model and make it accessible via an API for seamless integration into various financial applications. Future work will also involve exploring more advanced transformer architectures and potentially expanding the range of expense categories the model can identify.</p>

</body>
</html>
