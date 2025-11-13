EU Debates Knowledge Graph & NLP Pipeline
Group Members

Riya Pokharel

Amisha Magar

Sristi Kulung Rai

Overview

This assignment applies an end-to-end NLP and network analysis pipeline to the EU Parliament Debates dataset.
We use an LLM to extract structured information from speeches and then construct a simple knowledge graph (speaker → topic) to analyze discussion patterns in the parliament.

Dataset

Source: RJuro/eu_debates (Hugging Face)

Subset: Small random selection of speeches to keep the analysis manageable

Reason: EU debates contain rich information about speakers, parties, and issues, making them suitable for experimentation with LLM extraction and network analysis.

 LLM-Based Structured Extraction

We used an external LLM API :

Speaker name

Political party

Main topic discussed in the speech

A structured schema was used so the LLM returned clean and consistent fields.
The extracted results were stored in a pandas DataFrame.

 Descriptive Exploration

We performed basic descriptive analysis:

Frequency counts of extracted topics

A Top 10 topics bar chart

Manual inspection of a few extractions to check LLM accuracy

Some topic outputs were vague or noisy, which is expected for LLM-based extraction.

Knowledge Graph / Network Construction

We built a bipartite speaker–topic network using NetworkX:

Nodes: Speakers and topics

Edges: A link is created when a speaker mentions a topic

This provides a structural view of what issues are discussed.

 Network Analysis & Visualization

We calculated degree centrality to see which topics appear most across different speakers.

Visual outputs include:

Centrality bar chart

Simple network visualization

This helps identify the most prominent issues discussed in our sample.

Main Findings

Economy is the most central topic in our extracted subset.

Refugees, Human Rights, Environment, and Climate also appear frequently.

Even with extraction noise, the network gives insight into highly discussed issues.

Limitations

LLM sometimes mislabels or oversimplifies topics

Topics can overlap or be too broad

Only a small subset of the dataset was used, so findings are illustrative, not complete

File Structure

NLP_GROUP_ASSIGNMENT_noapikey.ipynb — main notebook (API key removed for safety)

eudebateswithtopics.csv — extracted structured dataset

plots/ — visualizations (if included)

README.md — this file

Conclusion

This assignment demonstrates how LLM-based extraction can be combined with network analysis to understand political speech data.
Even with imperfect extraction, the pipeline reveals useful patterns in which issues are widely discussed in the EU Parliament.