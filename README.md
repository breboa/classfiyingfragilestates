### Classifying Fragile Countries using The World Happiness Report*

For this classification project, I started out with a question rather than a dataset: can we predict in advance, which countries will be fragile (per the fragility report) and when, and deploy the necessary resources to stave off conflict, pain, and death? Ie. Are there features of importance in the development data that can be signals for the wellbeing of a country? 

About the dataset: the metric against which to train my classification algorithm would then be the Fragility Index. The Fragility Index is a yearly report which ranks countries on the index from 0-4, where 0 is sustainable and 4 is alert. Scores are calculated using 40-50 mil media articles and reports from 10,000+ sources, pre-existing quantitative datasets from the United Nations, World Bank, World Health Organization, etc, qualitative expert analysis, and independent  research review. 

Taking the fragility scores as my target, I then define my predictors using the features of the Happiness Report. Governments, multilateral stakeholders, and development experts increasingly consider happiness as the most indicative measure of a country's well-being, ie. social progress and a goal of public policy; not GDP. The World Happiness Report surveys around 2,000 to 3,000 people in 158 countries each year. Can we then use happiness to classify fragility?

I cleaned the data and then ran 4 classification models to find the best performing: Logistic Regression, Decision Tree, Random Forest, and KNN. KNN performed the best in test accuracy. Why? I have a small dataset, there is not a lot of noise in the data, KNN does not lose details as opposed to a DT or RF and the number of data points is greater than predictors/ features. I also ran a confusion matrix on the classification model to identify TYPE II ERROR, or what they call Unexpected Violence in the development literature - Classified Stable when Warning and Unexpected Resilience - Classified Alert when Warning. 

For stakeholders, Unexpected Resilience is of special interest for conflict prevention, capacity building, and strengthening countries. Specifically, why do certain countries who should be in turmoil per the indicators stave that off and how can stakeholders build more resilient countries and institutions in spite of shocks and global disruptions that affect all countries?

Finally, I also did a feature importance analysis of my classification model to glean insight into what contributes most to a country's fragility score. While insightful, there are some limitations concerning data quality to the impacts of the application of this model. First, this is a  small dataset (Only 158 Countries). A possible solution is to add historical data & treat each country  year as an independent data point. I also took the mean average of happiness predictor scores where a possible solution is to treat each year's data independently and concat with corresponding years from the fragility report.

Note: I originally thought to use the UN's development data to classify fragility against a country's fragility ranking. However, the inconsistencies and sparseness of the UN data made it ineffective to use (as column data for a country would be missing one year and not the next), made it not robust for the classification model as seen in the accuracy scores for notebooks 'Classifiying Fragility Using UN...etc'. I did decide to keep the UN-based notebooks in this project, however, because they were useful learning many data wrangling techniques.

References:
https://fragilestatesindex.org/
https://apolitical.co/solution_article/move-over-gdp-global-happiness-rankings-are-the-metric-of-the-future/
