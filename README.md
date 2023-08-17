# uncertainity_in_LLMs

## Overview
This repository delves into the realm of uncertainty quantification within the context of Large Language Models (LLMs) and Natural Language Generation (NLG). The primary focus is on the paper "Generating with Confidence: Uncertainty Quantification for Black-box Large Language Models", which highlights the challenges of uncertainty in NLG.

## Table of Contents
1. Introduction
2. Preliminaries
3. Infrastructure
4. Modules
5. Results

## Introduction
LLMs, or Large Language Models, are trained on vast volumes of text data, enabling them to generate human-like text based on input. NLG, or Natural Language Generation, is the process of creating human-like language using computers. This project aims to bridge the gap between understanding how to trust models and determining how uncertain or confident these models are in their responses.

## Preliminaries
Uncertainty Vs Confidence
Uncertainty: Refers to the dispersion in the posterior distribution of a predicted outcome. It's quantified using predictive entropy.

Confidence: Represents the predicted probability of an outcome, considering both the input and the output. It's distinct from uncertainty and is often misconstrued as its opposite.

Entailment and NLI: Natural Language Inference (NLI) is the essence behind chatbots and dialogue systems, helping them understand and respond to user inputs.

Rouge Scores: A metric to evaluate the similarity between machine-generated summaries and the original text.

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

compute_neg_log_likelihoods: Computes negative log-likelihoods and embeddings for primary and secondary likely generations.
generate_uncertainty: Examines a selection of responses to gauge the model's capability in determining the accuracy of generated answers.
generate_confidence: Measures the system's confidence in its responses.
Results
Our study indicates that using similarities from an NLI model, along with metrics assessing dispersion, effectively identifies challenging questions and confident answers. The OPT-350M model outperforms the OPT-125M model in all metrics for the CoQA dataset. However, there are certain limitations and challenges associated with our work that still need to be addressed.

## Acknowledgments
We would like to acknowledge the authors of the paper "Generating with Confidence: Uncertainty Quantification for Black-box Large Language Models" for their invaluable insights and contributions to the field.
