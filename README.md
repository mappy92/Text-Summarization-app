# 📝 Text Summarization Pipeline using PEGASUS (SAMSum Dataset)

## Table of Contents
1. Project Scope  
2. Audience-Friendly Description  
3. Business Impact  
4. Project Description  
5. Folder Structure  
6. Flow Diagram  
7. Demo Video  
8. Output  
9. How to Run & Dependencies  
10. Contribution Guidelines  
11. License & Credits  
12. Next Steps  

---

## 1. Project Scope

This project implements an **end-to-end NLP pipeline** for **abstractive text summarization** using the **PEGASUS transformer model**.  
It covers the complete machine learning lifecycle:

- Remote data ingestion  
- Dataset validation  
- Tokenization and transformation  
- Model training using Hugging Face Trainer  
- Model evaluation using ROUGE metrics  

The pipeline is modular, configurable, and suitable for production-scale workflows.

---

## 2. Audience-Friendly Description

Think of long chat conversations that need to be summarized into short, meaningful insights.

This project:
- Takes raw conversational data  
- Prepares it for machine learning  
- Trains a state-of-the-art NLP model  
- Generates concise summaries  
- Evaluates summary quality automatically  

All steps are automated and reusable.

---

## 3. Business Impact

- Automates summarization of conversations and transcripts  
- Reduces manual summarization effort  
- Improves operational efficiency  
- Scales easily for large datasets  
- Leverages pretrained models to reduce cost and time  

**Applicable Use Cases**:
- Customer support chat summarization  
- Call center analytics  
- Conversational AI systems  
- Documentation automation  

---

## 4. Project Description

The system consists of five core stages:

### Data Ingestion
- Downloads dataset from a remote URL
- Avoids re-downloading existing files
- Extracts compressed ZIP files

### Data Validation
- Checks presence of required dataset files
- Writes validation status to a report file
- Prevents invalid data from entering the pipeline

### Data Transformation
- Tokenizes dialogue and summary pairs
- Converts text into model-compatible tensors
- Stores transformed datasets on disk

### Model Training
- Fine-tunes the PEGASUS model
- Uses Hugging Face Trainer
- Supports GPU acceleration
- Saves trained model and tokenizer

### Model Evaluation
- Generates summaries on test data
- Computes ROUGE-1, ROUGE-2, ROUGE-L, ROUGE-Lsum
- Stores evaluation metrics as CSV

---

## 5. Folder Structure

<pre>

  ├── artifacts/
│ ├── data_ingestion/
│ │ └── samsum_dataset/
│ ├── data_transformation/
│ │ └── samsum_dataset/
│ ├── model_trainer/
│ │ └── pegasus-samsum-model/
│ └── model_evaluation/
│ └── rouge_scores.csv
│
├── config/
│ ├── data_ingestion.yaml
│ ├── data_validation.yaml
│ ├── data_transformation.yaml
│ ├── model_trainer.yaml
│ └── model_evaluation.yaml
│
├── src/
│ ├── data_ingestion.py
│ ├── data_validation.py
│ ├── data_transformation.py
│ ├── model_trainer.py
│ └── model_evaluation.py
│
├── README.md
├── requirements.txt
└── main.py
</pre>


---

## 6. Flow Diagram

<pre>

Remote Dataset (ZIP)
↓
Data Ingestion
↓
Data Validation
↓
Data Transformation (Tokenization)
↓
Model Training (PEGASUS)
↓
Model Evaluation (ROUGE)
↓
Saved Model & Metrics
  
</pre>


---

## 7. Demo Video

Demo includes:
- Dataset download & extraction
- Training execution
- Summary generation
- ROUGE score output

(Add GIF or video link here)

---

## 8. Output

### Model Artifacts
- Trained PEGASUS model
- Tokenizer files

### Evaluation Metrics
Saved as CSV:

artifacts/model_evaluation/rouge_scores.csv


ROUGE Metrics:
- ROUGE-1
- ROUGE-2
- ROUGE-L
- ROUGE-Lsum

---

## 9. How to Run & Dependencies

### Prerequisites
- Python 3.8+
- CUDA-enabled GPU (optional)

### Install Dependencies
pip install -r requirements.txt

### Run Pipeline
python main.py

### Key Libraries
- transformers
- datasets
- torch
- evaluate
- pandas
- tqdm

---

## 10. Contribution Guidelines

- Fork the repository  
- Create a feature branch  
- Follow PEP8 standards  
- Add tests where applicable  
- Submit a pull request  

---

## 11. License & Credits

**License**: MIT  

**Credits**:
- Hugging Face Transformers  
- SAMSum Dataset  
- PEGASUS Research  

---

## 12. Next Steps

Planned improvements:
- Add inference API using FastAPI  
- Experiment with T5 and BART models  
- Add MLflow experiment tracking  
- Hyperparameter tuning  
- Dockerize the pipeline  
- Cloud deployment (Azure / AWS)  
