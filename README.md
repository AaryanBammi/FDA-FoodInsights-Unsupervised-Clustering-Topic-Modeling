# FDA Food Insights – Unsupervised Clustering & Topic Modelling

## Overview
This project applies unsupervised machine learning techniques to explore patterns in FDA food event data. Through dimensionality reduction (Truncated SVD, UMAP), K‑means clustering, and non‑negative matrix factorisation (NMF) topic modelling, it uncovers relationships and themes within unstructured text reports.

## Data
The FDA Food Event dataset contains reports of adverse food events with textual descriptions, dates and categorical attributes. The full dataset is large (> 8 MB); only sample code is provided here. You may obtain the dataset from the FDA open data portal.

## Methodology
1. **Data cleaning:** Remove duplicates, filter for relevant report types and extract text fields.
2. **Vectorisation:** Convert cleaned text into TF–IDF features and apply Truncated SVD or UMAP for dimensionality reduction.
3. **Clustering:** Perform K‑means clustering on the reduced embeddings to group similar reports.
4. **Topic modelling:** Use NMF on the TF–IDF matrix to extract coherent topics and top terms for each cluster.
5. **Visualisation:** Plot 2D embeddings coloured by cluster and display bar charts of top words per topic.

## Key Insights
- Distinct clusters correspond to contamination types (e.g., allergen, pathogen, foreign material).
- Topics reveal patterns such as product categories (nuts, dairy), hazard types and common symptoms.
- Dimensionality reduction improves interpretability and visualisation of text‑based clusters.

## Usage
1. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

2. Launch the notebook:

   ```bash
   jupyter notebook fda_foodinsights_clustering_topic_modeling.ipynb
   ```

3. Provide a CSV file of FDA food event reports (with a “description” column) and follow the notebook instructions to reproduce the analysis.

## Next Steps
- Experiment with other clustering algorithms (DBSCAN, hierarchical clustering).
- Use LDA or BERTopic for alternative topic modelling approaches.
- Integrate the findings into a dashboard for regulators and food producers.
