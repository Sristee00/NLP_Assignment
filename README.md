# 🇪🇺 EU Debates – LLM Extraction & Knowledge Graph Analysis

## 👥 Group Members
- **Riya Pokharel**
- **Amisha Magar**
- **Sristi Kulung Rai**

---

## 📌 Project Overview
This project applies an **end-to-end NLP and network analysis pipeline** to a subset of the **EU Parliament Debates** dataset.  
The goal was to experiment with:

- LLM-based information extraction  
- Descriptive text analysis  
- Knowledge graph construction  
- Network centrality analysis  

The outcome demonstrates how political speech data can be structured and analyzed to reveal major themes and connections between topics.

---

## 📚 Dataset

### **Source**
Dataset: **RJuro/eu_debates**  
Platform: *HuggingFace*

### **Subset Choice & Rationale**
We used a **small random subset** of debates rather than the full corpus because:

- The full dataset is large and computationally expensive  
- LLM extraction costs increase with dataset size  
- A smaller sample allows quick iteration and manual validation  
- Sufficient to demonstrate the methodology for this module  

---

## 🤖 LLM Extraction Process

We used an external LLM API to extract structured information from each speech.  
Each record includes:

- **Speaker name**
- **Political party** (when identifiable)
- **Main topic** (assigned by LLM)
- **Speech text**
- **Speech ID**

A strict **JSON schema** ensured consistent LLM output.

The results were stored in:

- `eu_debates_with_topics.csv` (final extracted dataset)

---

## 📊 Descriptive Exploration

We performed several descriptive steps:

- Frequency counts of extracted topics  
- Top 10 most common topics plot  
- Manual inspection to check LLM accuracy  

Extraction noise was expected: some topics were vague or labeled as `nan`.

---

## 🕸️ Knowledge Graph Construction

We built a **bipartite Speaker–Topic graph** with NetworkX:

- **Nodes:** Speakers & Topics  
- **Edges:** A connection exists when a speaker discusses a topic extracted by the LLM  

This structure helps visualize how political issues are shared across different members of parliament.

---

## 📈 Network Analysis

We computed:
- **Degree Centrality** for all topic nodes
<img width="794" height="658" alt="graph" src="https://github.com/user-attachments/assets/2bf0a2f5-7092-4733-a2a3-ea0c3fa2985c" />

This helps identify which issues dominate the political conversation.

---

## 🔍 Main Findings

### **Most Discussed Topics (LLM Extraction)**
<img width="767" height="470" alt="downloadjj" src="https://github.com/user-attachments/assets/e9cf5ae9-a28f-49a0-80ce-76281e29a75d" />

A large number of `nan` topics reflect extraction noise.

### **Most Central Topics (Network Perspective)**
<img width="637" height="455" alt="downloadNetwork" src="https://github.com/user-attachments/assets/199fc263-4a0d-4853-858f-79690c02481f" />

The network and topic frequency results align closely.

---

## ⚠️ Limitations

- **LLM noise:** Topics sometimes oversimplified or mislabeled  
- **Missing party info:** Often not explicitly stated in the speech text  
- **Small subset:** Results are **illustrative**, not representative  
- **Topic overlap:** Related topics (e.g., Climate vs. Environment) split across labels  

Despite this, the workflow successfully demonstrates the required methods.

---

## 📦 Generated Outputs

### **1️⃣ Extracted Structured Dataset**
`eu_debates_with_topics.csv`  
Contains all speaker–topic–party triples extracted by the LLM.

---

### **2️⃣ Visualizations (PNG)**  
Stored in the `plots/` folder.

- `topic_frequency.png` – Top 10 discussed topics  
- `speaker_topic_network.png` – Full Speaker–Topic network  
- `topic_centrality.png` – Top 10 most central topics  

These images come directly from the analysis notebook.

---

### **3️⃣ Notebook**
`NLP_M2.ipynb`  
Contains the entire pipeline:

- LLM extraction prompts  
- Parsing & cleaning  
- Topic counts  
- Network creation  
- Centrality computation  
- Plot generation  

---

## 📁 Repository Structure
├── eu_debates_with_topics.csv
├── NLP_M2.ipynb
├── plots/
│ ├── topic_frequency.png
│ ├── speaker_topic_network.png
│ └── topic_centrality.png
└── README.md


---

## ✅ Conclusion
This project successfully demonstrates how **LLMs + network analysis** can be used to structure and interpret political speech data.  
Even with imperfect extractions, the pipeline reveals central themes in EU parliamentary discourse and highlights the potential of LLM-based text analysis for social science research.


