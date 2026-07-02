# Financial Named Entity Recognition with Transformers

> A transformer-based Named Entity Recognition (NER) system developed for the Dunedain Machine Learning / NLP Research Engineer Challenge using the FiNER-ORD financial dataset.

---

## Overview

This project explores the application of transformer-based Natural Language Processing (NLP) to Financial Named Entity Recognition (NER). The objective was to identify and classify entities such as **people**, **organizations**, and **locations** within financial news articles.

The model was developed using the **FiNER-ORD** dataset from Hugging Face and fine-tuned with a pretrained BERT model using the Hugging Face Transformers library.

---

## Dataset

**Dataset:** [FiNER-ORD](https://huggingface.co/datasets/gtfintechlab/finer-ord)

The FiNER-ORD dataset contains token-level annotations for financial news articles.

Each token is labeled using the BIO tagging scheme:

| Label | Description |
|-------|-------------|
| O | Outside any entity |
| B-PER | Beginning of Person entity |
| I-PER | Inside Person entity |
| B-LOC | Beginning of Location entity |
| I-LOC | Inside Location entity |
| B-ORG | Beginning of Organization entity |
| I-ORG | Inside Organization entity |

Because the raw dataset is provided one token per row, the preprocessing pipeline reconstructs complete sentences before model training.

---

## Model

Final model used:

```
dslim/bert-base-NER
```

Rather than training from scratch, this project fine-tunes a pretrained Named Entity Recognition model and adapts it to the FiNER-ORD financial dataset.

To improve performance on the highly imbalanced dataset, the training pipeline incorporates **class-weighted cross entropy loss**, giving greater emphasis to underrepresented entity classes.

---

## Methodology

The training pipeline consists of:

- Loading the FiNER-ORD dataset using Hugging Face Datasets
- Cleaning invalid and missing tokens
- Reconstructing sentence-level samples from token-level records
- Converting labels into standard BIO format
- Tokenizing text using a pretrained BERT tokenizer
- Aligning word-level labels with tokenizer subwords
- Fine-tuning a transformer for token classification
- Evaluating predictions using entity-level Precision, Recall, and F1 Score

---

## Results

| Metric | Validation | Test |
|---------|-----------:|-----:|
| Precision | **0.9039** | **0.7747** |
| Recall | **0.9113** | **0.8481** |
| F1 Score | **0.9076** | **0.8097** |
| Accuracy | **0.9885** | **0.9816** |

---

## Example Prediction

Input:

```text
Apple CEO Tim Cook visited India after Microsoft announced earnings.
```

Output:

| Token | Prediction |
|------|------------|
| Apple | B-ORG |
| CEO | O |
| Tim | B-PER |
| Cook | I-PER |
| visited | O |
| India | B-LOC |
| after | O |
| Microsoft | B-ORG |
| announced | O |
| earnings | O |

---

## Technologies

- Python
- PyTorch
- Hugging Face Transformers
- Hugging Face Datasets
- Google Colab
- pandas
- NumPy
- scikit-learn
- seqeval

---

## Repository Structure

```
financial-ner-transformer/
│
├── financial_ner_challenge.ipynb
├── README.md
├── requirements.txt
│
└── results/
    └── results_summary.md
```

---

## Running the Project

1. Install dependencies

```bash
pip install -r requirements.txt
```

2. Open the notebook

```
financial_ner_challenge.ipynb
```

3. Run all notebook cells to:

- Load the dataset
- Preprocess financial text
- Fine-tune the transformer
- Evaluate model performance
- Generate sample predictions

---

## Key Takeaways

This project demonstrates practical experience with:

- Transformer-based Natural Language Processing
- Financial text mining
- Named Entity Recognition (NER)
- Token classification
- Data preprocessing pipelines
- Class imbalance handling
- Model evaluation using entity-level metrics
- Hugging Face machine learning workflows

---

## Acknowledgements

- Dunedain Machine Learning / NLP Research Engineer Challenge
- Hugging Face Transformers
- Hugging Face Datasets
- FiNER-ORD Financial Named Entity Recognition Dataset
