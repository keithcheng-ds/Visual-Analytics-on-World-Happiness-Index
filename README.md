# Impact of COVID-19 on World Happiness📊

## Abstract

This year marks the fourth since the onset of the COVID-19 pandemic. During this period, societies across the globe experienced major transformations. This study investigates the impact of COVID-19 on global happiness using time series analysis, clustering, and correlation heatmaps. While overall happiness index scores did not show significant year-over-year changes, we observed a shift in patterns across countries. Some factors became more influential in determining happiness scores.

---

## 1. Problem Statement

Since the World Health Organization declared COVID-19 a global pandemic in March 2020 [1], governments worldwide implemented various restrictions, profoundly altering social dynamics. Beyond the fear of infection, individuals faced challenges such as vaccine controversies, lockdowns, travel bans, and social distancing. These measures reshaped daily habits, hygiene awareness, and interpersonal interactions. Social isolation, particularly due to distancing guidelines, intensified.

To understand the pandemic's impact on human well-being, we analyze data from the *World Happiness Report*, a publication by the Sustainable Development Solutions Network based on Gallup World Poll data. The report ranks and analyzes approximately 150 countries based on happiness scores [2].

This study aims to answer the following research questions:

1. How did global happiness change before and after the COVID-19 pandemic?
2. Has the importance of the factors contributing to happiness scores changed since the pandemic?

We use a dataset spanning from 2015 to 2022, covering 146 countries, to facilitate a pre- and post-pandemic comparison.

---

## 2. State of the Art

The *World Happiness Report* was first published in 2012 and has since been released annually. It provides insights into global happiness trends and offers policy recommendations for enhancing well-being. The report evaluates factors such as health, social support, freedom, government corruption, and GDP per capita. Its aim is to equip governments and policymakers with empirical data to assess and improve quality of life.

In two relevant studies we reviewed [3][4], both employed visual analytics to explore happiness-related questions. One study [3] incorporated supplementary datasets, including the *World Values Survey* and other public opinion data, to explore relationships between life satisfaction, income, freedom, and health indicators. Their visualizations—interactive charts, scatter plots, and maps—demonstrated that wealthier countries (e.g., Finland, Denmark, Iceland, Switzerland, and the Netherlands) generally scored higher in happiness.

Another study [4] focused on creating intuitive visualizations to allow users to explore global happiness trends. Using choropleth maps and interactive charts, they supported user tasks such as identifying countries with extreme scores, viewing regional trends, and analyzing factor distributions.

From these studies, we learned effective methods for interpreting happiness data, comparing features via correlation analysis, and visualizing results for meaningful interpretation.

---

## 3. Data Properties

The *World Happiness Report* assesses happiness based on six key factors:
- GDP per capita  
- Healthy life expectancy  
- Freedom to make life choices  
- Social support  
- Generosity  
- Perception of corruption

These factors are derived from Gallup World Poll responses using the Cantril ladder method [5], where respondents rate their lives on a scale from 0 (worst) to 10 (best) [6]. Each country's sample includes approximately 1,000 respondents per year.

We obtained the dataset from Kaggle, which compiles World Happiness Report data from 2015 to 2022. It contains 12 columns and 1,229 rows, including country, region, happiness rank, score, and the six factors.

To assess data quality, we plotted histograms and boxplots. GDP per capita followed a roughly normal distribution. Social support, life expectancy, and freedom showed slightly right-skewed distributions, while generosity and corruption were left-skewed. Outliers were retained, as each row represents a unique country and is meaningful to our analysis.

We removed two columns—row index and happiness rank—as they were not relevant to our study. No missing values were found in the dataset.

For analysis, we split the data into two subsets:
- **Pre-COVID** (2015–2019)  
- **Post-COVID** (2020–2022)

This segmentation facilitated visualization and comparative analysis. Distributions within each subset closely resembled the overall dataset.

---

## 4. Analysis

### 4.1 Approach

To address our research questions, we conducted a comparative analysis of the pre- and post-COVID datasets using various visualization techniques. The process involved data preprocessing, exploratory data analysis, and clustering.

We completed three main tasks:
- **Task 1**: Time series analysis of happiness scores and factor trends over time.
- **Task 2**: K-means clustering to group countries by happiness-related features before and after the pandemic.
- **Task 3**: Correlation analysis between happiness scores and contributing factors.

---

### 4.2 Process

#### Task 1: Time Series Analysis

We grouped the data by year and calculated average values for each factor. The time series visualization includes a red divider at 2019 to mark the pre- and post-pandemic period.

**Findings:**
- Happiness scores remained relatively stable with a slight increase from 2019 to 2022.
- Social support dropped to 2016 levels in 2021, swapping positions with GDP per capita.
- GDP per capita reached a peak in 2022.
- Life expectancy declined slightly starting in 2019.
- Freedom to make life choices increased modestly post-COVID.

We also visualized regional trends using the "Region" attribute to avoid clutter. Again, no dramatic regional changes were observed, though Australia and New Zealand consistently reported the highest happiness scores.

---

#### Task 2: K-means Clustering

We used K-means clustering to identify groups of countries with similar happiness profiles. The analysis was performed separately for the two data subsets.

We used silhouette plots to determine the optimal number of clusters (K = 4).

**Observations:**
- Pre-COVID clusters grouped countries like the U.S., Canada, Western Europe, and Australia together.
- Post-COVID clustering revealed a major shift, with countries like China and Mexico moving to different clusters.
- The clustering distribution became more uniform post-COVID, indicating convergence in happiness profiles.

---

#### Task 3: Correlation Analysis

We examined how the relationship between happiness score and contributing factors changed post-COVID using scatter plots and heatmaps.

**Pre-COVID (2015–2019):**
- Highest correlation: GDP per capita (0.79)
- Followed by: Life expectancy (0.74), Social support (0.65)
- Lowest: Generosity (0.14)

**Post-COVID (2020–2022):**
- Highest correlation: Life expectancy (0.71)
- GDP per capita’s correlation declined
- Generosity remained the lowest

This may reflect a shift in values, with health and longevity becoming more important after the pandemic.

---

## References

[1] Brannen, S., Ahmed, H., & Newton, H. (2020). Covid-19
Reshapes the Future. Center for Strategic and International
Studies (CSIS). http://www.jstor.org/stable/resrep25198

[2] Helliwell, J. F., Layard, R., & Sachs, J. D. (2012, April 4). World
happiness report 2012. The World Happiness Report. Retrieved
from https://worldhappiness.report/ed/2012/

[3] Esteban Ortiz-Ospina and Max Roser (2013) - "Happiness and
Life Satisfaction". Published online at OurWorldInData.org.
Retrieved from: 'https://ourworldindata.org/happiness-and-life-
satisfaction' [Online Resource]

[4] Bazurto-Gomez, N. et al. (2019). An Information Visualization
Application Case to Understand the World Happiness Report. In:
Agredo-Delgado, V., Ruiz, P. (eds) Human-Computer
Interaction. HCI-COLLAB 2018. Communications in Computer
and Information Science, vol 847. Springer, Cham.
https://doi.org/10.1007/978-3-030-05270-6_4

[5] Levin, K.A., Currie, C. (2014) Reliability and Validity of an
Adapted Version of the Cantril Ladder for Use with Adolescent
Samples. Soc Indic Res 119, 1047–1063.
https://doi.org/10.1007/s11205-013-0507-4


[6] FAQ. (n.d.). Retrieved from https://worldhappiness.report/faq/

[7] Hartigan, J. A., & Wong, M. A. (1979). Algorithm AS 136: A K-
Means Clustering Algorithm. Journal of the Royal Statistical
Society. Series C (Applied Statistics), 28(1), 100–108.
https://doi.org/10.2307/2346830

[8] K. R. Shahapure and C. Nicholas (2020), "Cluster Quality
Analysis Using Silhouette Score," 2020 IEEE 7th International
Conference on Data Science and Advanced Analytics (DSAA),
2020, pp. 747-748, doi: 10.1109/DSAA49011.2020.00096.

[9] Tomar, A. (2022). Stop using elbow method in k-means
clustering, instead, use this! Medium. Retrieved from
https://towardsdatascience.com/elbow-method-is-not-sufficient-
to-find-best-k-in-k-means-clustering-fc820da0631d

[10] Sklearn.cluster.kmeans. scikit. (n.d.). Retrieved from
https://scikit-
learn.org/stable/modules/generated/sklearn.cluster.KMeans.html

[11] Annabel, Kay. (n.d.). The Science of Happiness – A Visual
Exploration. Retrieved from
https://moodle.city.ac.uk/pluginfile.php/2808074/mod_resource
/content/1/117002361-
166227_Annabel_Kay_Individual_Project_-
_Annabel_Kay_1418814_906946061.pdf

DATA
World Happiness Report 2015 to 2022.
Retrieved from
https://www.kaggle.com/datasets/mayzannilarthein44/world-
