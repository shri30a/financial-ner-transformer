# Financial Named Entity Recognition with Transformers

## Overview
This project was completed as part of a Dunedain machine learning challenge focused on building an NLP system for financial named entity recognition. The goal was to identify and classify entities such as people, organizations, and locations from financial text using token-level classification.

## Problem
Financial documents contain dense, domain-specific language, making entity extraction difficult with rule-based methods. This project explores a transformer-based approach to improve entity recognition accuracy and generalization.

## Dataset
The project used the FiNER-ORD dataset, a financial NER dataset with token-level labels for entity recognition tasks.

## Approach
- Preprocessed token-level financial text data
- Used BIO-style tagging for named entity labels
- Fine-tuned a transformer-based token classification model
- Evaluated performance using precision, recall, and F1 score
- Analyzed common errors around entity boundaries and class imbalance

## Tech Stack
- Python
- PyTorch / Hugging Face Transformers
- scikit-learn
- pandas
- NumPy
- Jupyter Notebook

## Key Features
- Transformer-based NER pipeline
- Financial-domain text processing
- Token classification training workflow
- Model evaluation using entity-level metrics
- Error analysis for improving entity extraction

## Results
The model demonstrated the ability to extract structured entities from financial text and highlighted the importance of domain-specific preprocessing, class balance, and boundary-aware evaluation in NLP systems.

## Repository Structure
