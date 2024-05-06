# Multiple Choice Question Answering with Layers of LLMs

This repository contains code to analyze the effects of different layers of a Large Language Model (LLM) on the results of multiple-choice question answering. The model used here is the **Mistral-7B-Instruct-v0.2**. The goal of the project is to evaluate the accuracy of each layer's output.

## Getting Started

### Prerequisites

To install the required Python packages, run the following commands:

```bash
pip install transformers accelerate peft bitsandbytes einops chardet datasets
```

# Usage

Load the Model and Dataset: The code starts by loading the pre-trained LLM model and tokenizer using Hugging Face Transformers. The dataset used is in JSON format and should be modified as per the desired data source.
Greedy Decoding: The greedy_decoding function allows generating text sequences using a greedy approach where only the most probable token is selected.
Beam Search with Layer: The beam_search_with_layer function allows evaluating the model's output from specific layers by using beam search for decoding.
Extracting Answers: The extract_answer function helps parse the model's responses to extract the answers based on predefined patterns.
Generate Layer Responses: The generate_layer_responses function applies the beam search for multiple layers and appends the generated responses to the dataset.

# Running the Script

Modify data_path: Update the data_path to point to the dataset file.
Run the Script: Execute the code to perform beam search and generate responses for multiple layers of the LLM.
Analyze the Results: The resulting dataset with responses from each layer will be saved to a CSV file, which can be analyzed further.
