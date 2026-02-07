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

