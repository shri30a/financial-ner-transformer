# Results Summary

## Model
- Model: `dslim/bert-base-NER`
- Task: Financial Named Entity Recognition
- Dataset: `gtfintechlab/finer-ord`
- Approach: NER-pretrained BERT with class-weighted loss

## Dataset Processing
The original dataset was provided as token-level rows. I reconstructed sentence-level examples by grouping tokens using `doc_idx` and `sent_idx`, then converted the labels into standard BIO format for evaluation.

## Results

| Split | Precision | Recall | F1 | Accuracy |
|---|---:|---:|---:|---:|
| Validation | 0.9039 | 0.9113 | 0.9076 | 0.9885 |
| Test | 0.7747 | 0.8481 | 0.8097 | 0.9816 |

## Key Techniques
- Token-level preprocessing
- Sentence reconstruction
- BIO label mapping
- Hugging Face Transformers fine-tuning
- Class-weighted loss for label imbalance
- Entity-level evaluation with seqeval

## Demo Prediction
Example sentence:

`Apple CEO Tim Cook visited India after Microsoft announced earnings.`

Predictions:
- Apple: B-ORG
- Tim: B-PER
- Cook: I-PER
- India: B-LOC
- Microsoft: B-ORG
