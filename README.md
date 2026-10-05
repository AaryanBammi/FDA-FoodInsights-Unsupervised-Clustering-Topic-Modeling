# FDA Adverse Event Reports: Clustering & Topic Modeling

Unsupervised analysis of about 120K FDA CAERS adverse event reports (foods, supplements, cosmetics) to group reports by reaction and outcome and surface which event types are most severe and slowest to reach the regulator.

**Stack:** Python, scikit-learn (TF-IDF, TruncatedSVD, K-Means, NMF), UMAP, Plotly  
**Context:** Team 11 project, Unsupervised Machine Learning, BU Questrom. Developers: Aaryan Bammi, Pratik Mahajan, Raskirt Singh Bhatia, Saketh Bolina.

## Data
[FDA CAERS food, supplement and cosmetic adverse event reports](https://open.fda.gov/data/caers/): 120,329 reports with reactions, outcomes, product, industry and consumer age. Cosmetics and vitamins/supplements make up most of the volume. The CSV is not included.

## Approach
- Cleaned the data and standardised consumer age across mixed units (days, weeks, months, years, decades)
- Cleaned the free-text `reactions` and `outcomes` fields and built TF-IDF features, plus frequency-encoded brand and one-hot categorical features (182 features)
- Reduced to 50 dimensions with TruncatedSVD (UMAP for 2D views) and clustered with K-Means; picked k = 3 from elbow and silhouette scores
- Fitted a 10-topic NMF model and labelled each topic, then profiled topics by consumer age and days to report

## Key findings
- Ten readable topics emerged, such as skin and allergic reactions, abdominal and gastro issues, ER visits, hospitalisation, and cancer
- Cancer-related and fatal-outcome reports take far longer to reach the FDA (around 3,200 to 3,400 days on average) than ER-visit or gastro reports (around 90 to 110 days), which points to long-latency harms going unreported for years
- Fatal-outcome reports involve the oldest consumers on average (about 61 years)

## Repo contents
- `Consolidated_Code.ipynb`: full analysis
- `requirements.txt`
