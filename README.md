# Quantifying Uncertainity in Large Language Models (LLMs)

## Overview
This repository delves into the realm of uncertainty quantification within the context of Large Language Models (LLMs) and Natural Language Generation (NLG). The primary focus is on the paper "Generating with Confidence: Uncertainty Quantification for Black-box Large Language Models", which highlights the challenges of uncertainty in NLG.

## Table of Contents
1. Introduction
2. Implementation
3. Preliminaries
4. Infrastructure
5. Modules
6. Results

## Introduction
LLMs, or Large Language Models, are trained on vast volumes of text data, enabling them to generate human-like text based on input. NLG, or Natural Language Generation, is the process of creating human-like language using computers. This project aims to bridge the gap between understanding how to trust models and determining how uncertain or confident these models are in their responses.

## Implementation

The step-by-step implementation of the project is as follows:
  1. Download the CoQA dataset and convert it into Huggingface Dataset format using the **coqa_setup.ipynb**
  2. Use the **generate_response.ipynb** notebook to generate the responses for the pre-trained LLM that is to be studied. Tha parameters and the choice of the models can be set at the very beginning of every notebook under the model **param**'s parameter
  3. To clean the responses received, use the **cleaner.ipynb** notebooks
  4. Utilize the cleaned generated responses to get the similarity scores using the **generate_similarities_for_model.ipynb** notebook
  5. Also utilize the cleaned generated responses to get the AUROC score and get the uncertainty using the **generate_uncertainity.ipynb** notebook
  6. Utilize the cleaned generated responses and their respective similarities score using the **generate_log_liklihood.ipynb** notebook
  7. Finally, use the **generate_confidence.ipynb** and **results.ipynb** notebooks to get the accuracy and score for the model

## Preliminaries
- Uncertainty Vs Confidence
  -  Uncertainty: Refers to the dispersion in the posterior distribution of a predicted outcome. It's quantified using predictive entropy.

  -  Confidence: Represents the predicted probability of an outcome, considering both the input and the output. It's distinct from uncertainty and is often misconstrued as its opposite.

- Entailment and NLI: Natural Language Inference (NLI) is the essence behind chatbots and dialogue systems, helping them understand and respond to user inputs.

- Rouge Scores: A metric to evaluate the similarity between machine-generated summaries and the original text.

## Infrastructure
The optimal infrastructure for NLP projects involves a trade-off between cost, performance, and scalability. Choices range from local setups, Google Colab, to AWS services, each with its advantages and disadvantages.

## Modules
Pre-Processing and Generate Responses
This module processes datasets into a tokenized format suitable for the model. It then generates responses to dataset prompts using various decoding methods and benchmarks them against reference answers.

Generating Similarities
Theory: Measuring similarities between response tokens from an LLM can be achieved using Jaccard similarity or NLI models.

Implementation: This module evaluates text responses produced by language models for their semantic and syntactic similarity.

Semantic Entropies
Theory: Uncertainty can be quantified using the number of semantic sets derived from similarities in the NLI model.

## Implementation: 

This section comprises multiple sub-modules:

1. compute_neg_log_likelihoods: Computes negative log-likelihoods and embeddings for primary and secondary likely generations.
2. generate_uncertainty: Examines a selection of responses to gauge the model's capability in determining the accuracy of generated answers.
3. generate_confidence: Measures the system's confidence in its responses.

## Results
Our study indicates that using similarities from an NLI model, along with metrics assessing dispersion, effectively identifies challenging questions and confident answers. The OPT-350M model outperforms the OPT-125M model in all metrics for the CoQA dataset. However, there are certain limitations and challenges associated with our work that still need to be addressed.

## Acknowledgments
We would like to acknowledge the authors of the paper "Generating with Confidence: Uncertainty Quantification for Black-box Large Language Models" for their invaluable insights and contributions to the field.
