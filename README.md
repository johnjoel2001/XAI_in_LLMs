# Analysis of Prompts with XAI Techniques

## Overview
- In this assignment, we use Explainable AI (XAI) methods to study how a language model (DistilGPT-2) responds to the sentence: "The quick brown fox jumps over the lazy dog!"
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


## Installation and Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/johnjoel2001/XAI_in_LLMs.git
   cd XAI_in_LLMs
   ```
2. Run the `XAI_in_LLMs.ipynb`
3. The requirements are listed in the first cell

**References**

1) https://arxiv.org/abs/2405.06064

2) https://medium.com/@alaeddineayadi/advanced-techniques-in-explainable-ai-xai-for-a-responsible-large-language-models-4c472fde996e

**Notes**

1) 

```
  perturbed_input = " ".join(perturbed)
  perturbed_output = model(perturbed_input, max_length=50, num_return_sequences=1)[0]['generated_text']
```
Three three lines of code were generated using Grok on 03/26/25 at 09:00 pm.

2) Apart from this, AI was not used in this notebook.
