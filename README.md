# Multiple Choice Question Answering with Layers of LLMs

This repository contains code to analyze the effects of different layers of a Large Language Model (LLM) on the results of multiple-choice question answering. The model used here is the **Mistral-7B-Instruct-v0.2**. The goal of the project is to evaluate the accuracy of each layer's output.

## Setup

To set up the project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/fatemehhaji/LLM-mcqa-layer-analysis.git

2. Create and activate a Virtual Environment.
3. Install Dependencies, including PyTorch, and also
   
   ```bash
   pip install transformers accelerate peft bitsandbytes einops chardet datasets
   ```

4. Run the notebooks:
- `generate_with_different_layers.ipynb`: Generate answers with different layers of the LLM

# Usage

1. Load the Model and Dataset: The code starts by loading the pre-trained LLM model and tokenizer using Hugging Face Transformers. The dataset used is in JSON format and should be modified as per the desired data source.
2. Beam Search with Layer: The beam_search_with_layer function allows evaluating the model's output from specific layers by using beam search for decoding.
3. Extracting Answers: The extract_answer function helps parse the model's responses to extract the answers based on predefined patterns.
4. Generate Layer Responses: The generate_layer_responses function applies the beam search for multiple layers and appends the generated responses to the dataset.

# Running the Script

Modify data_path: Update the data_path to point to the dataset file.
Run the Script: Execute the code to perform beam search and generate responses for multiple layers of the LLM.
Analyze the Results: The resulting dataset with responses from each layer will be saved to a CSV file, which can be analyzed further.
