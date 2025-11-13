# EU Debates Knowledge Graph & NLP Pipeline

## 👥 Group Members
- **Riya Pokharel**
- **Amisha Magar**
- **Sristi Kulung Rai**

---

## 📌 Overview
This project implements an end-to-end **NLP + Network Analysis pipeline** using the **EU Parliament Debates** dataset.  
We extract structured information from parliamentary speeches using an LLM and build a simple **knowledge graph** that connects speakers with the topics they discuss.

The project demonstrates:
- LLM-based information extraction  
- Basic descriptive text analysis  
- Knowledge graph construction  
- Network centrality analysis  

---

## 📚 Dataset
- **Source:** `RJuro/eu_debates` (Hugging Face)
- **Subset Used:** Small random sample of speeches
- **Why This Dataset?**  
  EU debates contain rich information about speakers, parties, and policy topics, which makes them ideal for experimentation with LLM extraction and network analysis on real political text data.

---

## 🤖 LLM-Based Structured Extraction
We used an external LLM API to extract the following fields from each speech:
- **Speaker name**
- **Political party**
- **Main topic discussed**

A structured schema ensured the LLM returned clean and consistent fields.  
The extracted outputs were stored in a **pandas DataFrame** for further analysis.

---

## 📊 Descriptive Exploration
We performed basic descriptive analysis, including:
- Topic frequency counts  
- A **Top 10 Topics** bar chart  
- Manual inspection of several LLM-extracted entries  

Some topic outputs were occasionally vague or noisy, which is expected with LLM-based extraction.

---

## 🕸️ Knowledge Graph / Network Construction
We built a **bipartite network** using NetworkX:

- **Nodes:** Speakers & Topics  
- **Edges:** A speaker is connected to a topic they mention  

This structure provides a visual and analytical understanding of who discusses what.

---

## 📈 Network Analysis & Visualization
We calculated **degree centrality** to identify which topics appear most frequently across the speakers in our dataset.

Generated visuals include:
- Degree centrality bar chart  
- Simple knowledge graph visualization  

These help highlight central topics in parliamentary discussions.

---

## 📝 Main Findings
- **Economy** is the most central and frequently discussed topic.
- Other prominent topics include:
  - **Refugees**
  - **Human Rights**
  - **Environment**
  - **Climate**
- Even with extraction noise, the network reveals meaningful patterns in debate topics.

---

## ⚠️ Limitations
- LLM sometimes mislabels, generalizes, or oversimplifies topics  
- Topic categories can be broad or overlapping  
- Only a **small speech subset** was analyzed — results are illustrative, not representative of the full dataset  

---

## 📁 File Structure
├── NLP_M2.ipynb # Main notebook (API key removed)
├── eu_debates_with_topics.csv # Extracted structured dataset
├── plots/ # Visualizations (charts, graphs)
└── README.md # Project documentation

---

## ✅ Conclusion
This assignment demonstrates how **LLM-based extraction** combined with **network analysis** can help uncover meaningful patterns in political speech data.  
Even with imperfect extraction, the pipeline provides insights into which topics dominate EU parliamentary debates.

---

