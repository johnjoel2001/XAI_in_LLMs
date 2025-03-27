# Analysis of Prompts with XAI Techniques

## Overview
- In this assignemnt, we use Explainable AI (XAI) methods to study how a language model (DistilGPT-2) responds to the sentence: "The quick brown fox jumps over the lazy dog!"
- Our goal is to find out which parts of the sentence like words, symbols, or word order are most important to the model.

## Methods Used
We tested the model with three methods:
1. **Perturbations**: We made big changes to the sentence, like removing the "!", mixing up the words, or changing "fox" to "cat," to see how the model’s response changes.
2. **Saliency Scores**: We checked each word to see which ones matter most by hiding one word at a time and looking at the difference.
3. **Counterfactuals**: We made small changes, like changing "!" to "?", repeating "quick," or changing "lazy" to "active," to see the effect.

We used cosine similarity to measure how much the model’s response changed and showed the results with bar charts.

## Tools and Setup
- **Model**: DistilGPT-2 (a small language model for generating text)
- **Libraries**: `transformers`, `sentence-transformers`, `matplotlib`, `numpy`
- **Prompt**: "The quick brown fox jumps over the lazy dog!"

## Key Findings
- **Perturbations**: Changing "fox" to "cat" made the biggest difference (score: 0.5245), showing words matter most. Removing "!" (score: 0.6338) and mixing up words (score: 0.7147) had less effect.
- **Saliency Scores**: "Quick" and "brown" were most important (scores: 0.75 to 0.8), meaning describing words matter a lot. The "!" mattered least (score: 0.65).
- **Counterfactuals**: Changing "!" to "?" changed the tone most (score: e.g., 0.7800), then changing "lazy" to "active" (score: e.g., 0.8200). Repeating "quick" had the least effect (score: e.g., 0.8500).

## Takeways
- The model cares most about the words, especially describing ones like "quick" and "brown." 
- Symbols like "!" change the tone, and word order matters less.
- Big changes to words have the largest impact, while small changes to symbols affect the tone the most.

## How to Run the Notebook
1. Open the Jupyter Notebook file (`AIPI_590_Assignment_10.ipynb`).
2. Install the required tools:  
   ```bash
   pip install transformers sentence-transformers matplotlib numpy
