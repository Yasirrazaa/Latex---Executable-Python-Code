# Latex -> Executable Python Code

## Project Overview
Converting **LATEX expressions** into **Python code** through **LLMs**.

---

## Steps

### 1. Synthetic Data Generation
- A synthetic dataset was generated using **Sympy** and **LLaMA 70B**.  
- The dataset is based on **8000 mathematical expressions** of 14 types including algebraic, logarithmic, and polynomial types.  
- More difficult ones like **Differentiation, Integration, Derivatives** were given a larger share in the dataset.  

### 2. Converting
- The dataset was converted into both **Textbook** and **JSON** format.  
- Evaluation showed that **JSON format** yielded better results.  

### 3. Choosing the Model
- The main LLM model chosen was **NuminaMath-7B-TIR**, a fine-tuned version of **deepseek-math-7b-base**.  
  - [NuminaMath-7B-TIR](https://huggingface.co/AI-MO/NuminaMath-7B-TIR)  
  - [deepseek-math-7b-base](https://huggingface.co/deepseek-ai/deepseek-math-7b-base)  

- This model was nominated **#1 in AI Math Olympiad 2024**, outperforming GPT and LLaMA due to **Self-Consistency with Tool-Integrated Reasoning (SC-TIR)**.  
- It performed well during inference without requiring a training dataset.  

**Other models tested:**
- **Phi** → performed well with “Textbook” format.  
- **T5** → tried due to encoder-decoder capabilities but results were not good.  
- **aimo_lora_v3** → used for training purposes.  
- **Prompt engineering** was used to improve results.  
- **Full model (non-quantized)** was used for best accuracy.  

---

## Problems Faced
- Validation of data produced by LLM was a challenge.  
- Post-processing issues caused **null values** due to:
  - Dataset code structure.  
  - Handling of negative logs.  

---

## References
- [AI Mathematical Olympiad - Progress Prize 1 | Kaggle](https://www.kaggle.com/competitions/ai-mathematical-olympiad-prize/discussion/519303)  
