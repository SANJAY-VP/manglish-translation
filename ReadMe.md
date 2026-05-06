# Manglish Code-Mixed Machine Translation

Repository for research and experimentation on **Manglish (Malayalam + English) code-mixed machine translation**, focusing on:
- transliteration challenges,
- noisy mixed-script inputs,
- multilingual MT models,
- and LLM-based translation approaches.

This repository contains:
- datasets,
- preprocessing pipelines,
- model outputs,
- evaluation artifacts,
- and the complete experimental notebook used in the study.

---

# Repository Structure

```text
.
├── CM_Dataset/                # Synthetic code-mixed dataset
├── CM_Output/                 # Translation outputs on CM dataset
├── CM_Evaluated/              # Evaluation results for CM outputs

├── Dataset/                   # Malayalam-English parallel dataset
├── Output/                    # Translation outputs on parallel dataset
├── Output_Evaluated/          # Evaluation results on parallel dataset

├── YT_CM                      # You Tube review dataset and translation outputs

├── main.ipynb                 # Main pipeline notebook
├── normalisation.ipynb        # Pipeline notebook for dataset-3 
├── README.md
```

---

# What is Implemented

The repository includes experiments involving:

## Transformer-Based MT Models
- IndicTrans2
- mBART
- mT5
- T5

## LLM-Based Translation
- GPT models
- Claude variants
- LLaMA variants
- Groq-hosted models

Both:
- zero-shot
- and few-shot

settings are evaluated.

---

# Datasets

## 1. Parallel Dataset (`Dataset/`)
Malayalam-English parallel corpus derived from Amazon reviews.

Used for:
- supervised MT training,
- fine-tuning,
- and baseline evaluation.

Characteristics:
- mostly clean Malayalam script,
- minimal code-mixing,
- structured parallel pairs.

---

## 2. Synthetic Code-Mixed Dataset (`CM_Dataset/`)
Artificially generated Manglish dataset with controlled code-mixing.

Includes:
- Latin-script Malayalam,
- inserted English tokens,
- mixed-script structures.

Used for:
- controlled robustness evaluation,
- code-mixed MT experiments,
- and transliteration analysis.

---

## 3. YouTube Code-Mixed Dataset (`YT_CM/`)

Real-world noisy Manglish dataset derived from YouTube comments.

This folder contains:
- transliteration experiments,
- IndicTrans outputs,
- Google Cloud Translation API outputs,
- and evaluation artifacts used for transliteration and robustness analysis.

Characteristics:
- noisy user-generated text,
- mixed Malayalam and English,
- inconsistent phonetic spellings,
- heavy script variation.

---

# Main Experimental Notebook

All major experiments are centralized in:

```text
main.ipynb
```

The notebook includes:
- preprocessing,
- dataset preparation,
- model loading,
- fine-tuning,
- prompting,
- inference,
- evaluation,
- and metric computation.

Pipeline flow:

```text
Dataset
   ↓
Preprocessing
   ↓
Translation / Generation
   ↓
Evaluation
```

---

# Evaluation Metrics

Implemented metrics:
- BLEU
- ROUGE
- METEOR
- chrF
- BERTScore

Evaluation outputs are stored separately for reproducibility.

---

# Important Research Findings

- Transliteration is the primary bottleneck in noisy Manglish MT.
- Fine-tuned MT models perform best on clean parallel data.
- LLM prompting is more robust to noisy code-mixed inputs.
- BLEU is unreliable for heavily code-mixed translation tasks.

---

# Running the Repository

## Environment
Recommended:
- Google Colab
- GPU runtime

## Install Dependencies

```bash
pip install transformers datasets evaluate sacrebleu bert-score rouge-score nltk sentencepiece
```

## Execute

Open:

```text
main.ipynb
```

and run cells sequentially.

---

# Notes for Reviewers

- Outputs and evaluated results are already included in the repository.
- Synthetic and parallel datasets are separated for clarity.
- The repository is organized to support:
  - reproducibility,
  - comparison across models,
  - and downstream experimentation.

---

# Future Extensions

Potential extensions include:
- transliteration-aware MT,
- COMET-based evaluation,
- CM-aware tokenization,
- larger Manglish corpora,
- and human evaluation pipelines.

