# Robust_MGT-Detectors

## Datasets:

We have three dataset folders. The label convention is as follows:
- **1**: Human-written text
- **0**: Machine-generated (AI-generated) text

### 1. Non-Paraphrased Data
#### **DEEP_FAKE(GPT_SPLIT)**
This dataset contains data from ten domains. It is used to train RODAM/CONDA and is split into source and target data, each containing:
- **Real (human-written) text**
- **Fake (machine-generated) text**
- **Train, validation, and test splits**

The machine-generated text in this dataset is GPT-generated. Additionally:
- **original_text** refers to the unaltered text.
- **perturbed_text** is generated using synonym replacement.

### 2. Paraphrased Data

#### **Paraphrasing Information:**
- **50%** of the AI-generated text is paraphrased, while the remaining half remains unchanged.
- The selection of AI text for paraphrasing is random.

#### **Dataset Structure:**
Each file in this dataset contains the following columns:
- **original_text**: The non-paraphrased text.
- **is_selected**:
  - **1**: The AI text was selected for paraphrasing.
  - **0**: The text was not selected for paraphrasing.
- **text**: The paraphrased version of the AI-generated text (if applicable); otherwise, it remains non-paraphrased.

#### **Datasets:**

##### i. **Deep Fake (Parpahrased_Test_Data)**
- The paraphrased test data includes paraphrased versions of GPT and LLaMA-generated text using a Pegasus-based paraphraser.

##### ii. **HCVAR**
**Dataset Overview:**
- We randomly sampled **2000** samples from each of the following domains from the [HCVAR dataset](https://huggingface.co/datasets/hannxu/hc_var):
  - Essay
  - News
  - Q&A
  - Review
- The dataset originally contained machine-generated text from GPT.
- We additionally generated text using **LLaMA** and **Mistral**.
- A portion of the AI-generated text was paraphrased using a Pegasus-based paraphraser.

##### iii. **Medical Data**
**Dataset Overview:**
- This dataset contains **2000** samples from three healthcare datasets:
  - **PubMed**
  - **MedQuAD**
  - **BioASQ**
- The dataset includes both human-written and machine-generated text using **LLaMA**.
- A portion of the AI-generated text has been paraphrased using a Pegasus-based paraphraser.

---

The main code for **RODAM** is also provided.
