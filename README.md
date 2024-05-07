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
   pip install transformers accelerate peft bitsandbytes einops chardet datasets matplotlib
   ```

4. Run the notebooks:
- `generate_with_different_layers.ipynb`: Generate answers with different layers of the LLM

### Data
The dataset is expected to be in a JSON format, tailored to multiple-choice question answering. Ensure that the data file is uploaded to the correct path you specify in the code.

**Sample Data:**
```json
{
  "examples": [
    {
      "input": "How many legs do horses have?",
      "target_scores": {
        "two": 0,
        "four": 1,
        "six": 0,
        "three": 0,
        "one": 0,
        "none": 0
      }
    },
    {
      "input": "How many eyes do horses have?",
      "target_scores": {
        "two": 1,
        "four": 0,
        "six": 0,
        "three": 0,
        "one": 0,
        "none": 0
      }
    }
  ]
}
```

# Usage

1. Load the Model: The code starts by loading the pre-trained LLM model and tokenizer using Hugging Face Transformers.
2. Beam Search with Layer: The beam_search_with_layer function allows evaluating the model's output from specific layers by using beam search for decoding.
3. Extracting Answers: The extract_answer function helps parse the model's responses to extract the answers based on predefined patterns.
4. Generate Layer Responses: The generate_layer_responses function applies the beam search for multiple layers and appends the generated responses to the dataset.

# Running the Script
To generate results:
- **Set Data Path:** Ensure the dataset is uploaded and the data path is correctly set in the code.
- **Run the Code:** Execute the code to perform beam search and generate responses.
- **Analyze Results:** Examine the dataset to see responses and answers generated for each layer.

## Results

We evaluated the accuracy of multiple-choice question answering across different layers of the Mistral-7B-Instruct-v0.2 Large Language Model (LLM). The results, presented below, show how accuracy varies as we progress through the layers:

- **Layer 8:** Accuracy was low, with no correct answers.
- **Layer 16:** Accuracy improved slightly, around 7% of questions answered correctly.
- **Layer 24:** Further improvement, with 10% of questions answered correctly.
- **Layer 32:** Best performance, about 47% of questions answered correctly.

Overall, accuracy improved progressively as the model processed deeper layers, suggesting that later layers contribute more effectively to accurate multiple-choice question answering.

## Observations

Even though the questions were simple, which models can usually answer easily, the results were worse in the multiple-choice format with one-shot examples. This suggests that the structure of multiple-choice questions and the one-shot prompting may have affected the model's performance.

