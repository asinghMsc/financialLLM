Tiny Transformer Language Model – Version 1

This repository contains the first version of a custom transformer-based language model, implemented entirely from scratch using PyTorch. The project focuses on building a lightweight, domain-specific LLM with full control over the model architecture, training workflow, and inference process — without relying on high-level frameworks or pretrained models.

The model was designed for structured text generation and trained on a bespoke dataset prepared externally. It runs efficiently within constrained environments such as Google Colab, and is well-suited for integration into lightweight inference systems or downstream automation tools.

Overview

Transformer decoder architecture implemented directly in PyTorch

Custom tokenisation pipeline using OpenAI’s tiktoken encoder (cl100k_base)

Full training loop with validation loss tracking and best-model checkpointing

Model supports standard autoregressive generation methods

Optimised for task-specific inference and future deployment

Dataset and preprocessing handled separately to maintain modularity and adaptability

Training Summary

The model was trained over 2,000 steps using a structured validation pipeline. Loss decreased consistently across the early stages of training, with best validation performance observed around step 1,300. Post-1,500 steps, performance stabilised with minor signs of overfitting, which is expected given the model's scale and tight scope.

The best-performing checkpoint is saved as best_model.pt for downstream use.

Architecture

The model follows a standard GPT-style layout with the following configuration:

Token and positional embeddings

Multi-head masked self-attention

Feed-forward MLP with ReLU activation

LayerNorm and residual connections throughout

4 layers, 4 heads, 128-dimensional embeddings

The implementation is intentionally minimal and production-aware, allowing for rapid adaptation to similar prompt-to-structure tasks.

Intended Use

This version was developed as a foundation for integrating small-scale, task-specific LLMs into production workflows — particularly those requiring structured output from unstructured or semi-structured input.

Next Steps

This project served as the foundation for a more advanced, production-ready version currently in development. That version builds further on this implementation with improved structure handling, better output consistency, and broader input flexibility. A SaaS product based on the model is also underway, with a planned release in the near future.
