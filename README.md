# CS6120-Summarization-Project
Katrina Truebenbach

### Description
TODO

### Data
CNN news articles: https://cs.nyu.edu/~kcho/DMQA/
- ~90,000 news articles from CNN 
- Includes raw text of each article and "highlight" sentences that can be concatenated to form a summary

### Conclusions
TODO 

### Repo Contents
Scripts in Run Order:
1. cnn_data: unzip and create dictionary from cnn data
2. exploratory_analysis: prepare raw data for analysis & perform exploratory analysis of articles and summaries.
3. compress_fasttext: compress FastText embeddings into a smaller object to fit RAM constraints at the cost of some accuracy
4. extractive_summarization_train: Train 3 different extractive summarization models (Baseline TF-IDF, TextRank, LSA) on a variety of configurations using a small subset of the data, select the best configuration for each evaluation metric for each model, and retrain on larger subset of data. Uses functions created in extractive_summarization.
5. abstractive_summarization: Apply the pre-trained T5 model to our data with a variety of configurations for decoding parameters using a small subset of the data, select the best configuration for each evaluation metric for each model, and re-decode a larger subset of the data. 
6. compare_extractive_models: for the best configurations trained in extractive_summarization_train, calculate the p-values of the difference between model's evaluation metrics and perform exploratory analysis of best models.


Visualization folder: html versions of bokeh visualizations created in exploratory_analysis and compare_extractive_models
