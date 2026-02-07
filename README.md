# Causal Analysis and Interactive Reasoning over Conversational Data

## 📌 Project Overview
This project implements an end-to-end system for **causal analysis and interactive reasoning** over multi-turn conversational transcripts. The system goes beyond simple outcome prediction by identifying **why an outcome occurred** using faithful, evidence-backed dialogue turns. It also supports multi-turn analytical queries.

---

## 🎯 Objectives
- Predict outcome events such as refunds, escalations, delays, and resolutions  
- Identify causal dialogue turns responsible for each outcome  
- Provide interpretable and traceable explanations  
- Support interactive follow-up queries with contextual consistency  
- Avoid hallucination through model-driven causal attribution  

---

## 🏗️ System Architecture

### 🔹 Stage 1 – Outcome Prediction
- Transformer-based (BERT) conversation classifier  
- Predicts final outcome of a conversation  

### 🔹 Stage 2 – Turn-Level Causal Attribution
- Leave-One-Out (LOO) confidence drop analysis  
- Assigns importance scores to dialogue turns  
- Extracts top-ranked turns as causal evidence  

### 🔹 Stage 3 – Interactive Query Handling
- Handles natural-language analytical queries  
- Maintains multi-turn query context  
- Returns structured explanations with evidence  

---

## 📂 Project Structure
├── structured_dataset.csv
├── queries.csv
├── results/
├── logs/
├── notebook.ipynb
├── requirements.txt
├── README.md


---

## 📊 Dataset Description

The dataset consists of structured conversational transcripts where each conversation contains multiple dialogue turns, and the outcome label is defined at the conversation level.

### Dataset Columns
- **transcript_id** → Unique identifier for each conversation  
- **turn_id** → Sequential order of dialogue turns  
- **speaker** → Speaker role (Agent or Customer)  
- **text** → Utterance content  
- **intent** → High-level issue category (e.g., delivery, appointment)  
- **domain** → Business domain  
- **reason** → Outcome explanation label  

### Preprocessing Notes
- Only spoken dialogue turns (Agent & Customer) are used  
- System summaries and metadata entries are excluded to prevent label leakage  

---

## ⚙️ Setup & Installation

### Environment Requirements
- Python 3.9 or higher  

### Create Virtual Environment

python -m venv venv
Execution Guide
###✅ Stage 1 – Outcome Prediction Training
Open the provided notebook
Run Stage 1 cells
Train BERT-based classifier
Best checkpoint is saved automatically in results/

###✅ Stage 2 – Turn-Level Evidence Extraction
Load trained model
Apply Leave-One-Out attribution
Rank dialogue turns by causal importance
Example Output
Importance Score: 0.79
Turn: Customer: The tracking shows delivered, but nothing arrived.

###✅ Stage 3 – Query-Driven Interaction
Example Queries
Why do delivery-related conversations result in refunds?
Which dialogue turn contributed most to the outcome?
System Behavior
Filters relevant conversations
Extracts causal evidence
Maintains context for follow-up queries

###📝 Query Dataset (queries.csv)
Contains:
Query ID
Query text
Query category
System output
Remarks explaining causal reasoning

###📈 Evaluation Metrics
Accuracy
Macro F1-score
Evidence faithfulness
Turn-level ID recall
##Stage 1 Results
Accuracy: 0.88
Macro F1-score: 0.80

###🔍 Faithfulness Guarantee
Model-driven Leave-One-Out causal attribution
Confidence-drop based importance scoring
Exact dialogue turns extracted as evidence
No generative hallucination used

###🔁 Reproducibility
Use provided dataset
Run notebook sequentially
Maintain same random seed
Use provided requirements.txt

###🔮 Future Work
Hierarchical turn-level Transformer models
Temporal modeling using timestamps
Visualization dashboards for causal evidence
Cross-conversation causal pattern mining

###📌 Conclusion
This project demonstrates how conversational machine learning systems can move beyond prediction toward causal, interpretable, and interactive reasoning. The approach is scalable, faithful, and aligned with real-world conversational analytics requirements.

###📬 Contact
Refer to the technical report or notebook documentation for additional details.
