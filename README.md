# CS6120-Summarization-Project
Katrina Truebenbach

### Description
This project aims to create an auto-summarization tool in the context of a management consulting content management workflow. The tool will generate summaries that content creators will review, edit, and accept.     
         
We have 3 primary goals:                 
- Capture the main themes of the content
- Preferentially provide too much information over too little information (high recall)
- Do not provide so much information that the task of editing down the summary is equivalent to producing a summary from scratch (reasonable precision)

### Data
Approximate confidential consulting materials with CNN news articles: https://cs.nyu.edu/~kcho/DMQA/
- ~90,000 news articles from CNN 
- Includes raw text of each article and "highlight" sentences that can be concatenated to form a summary

### Conclusions
- TextRank recall-optimized extractive summaries best achieve our stated goals
- Abstractive models such as T5 would be preferable if we did not have human editors because they produce more succinct, polished summaries, but in our context they are too high-risk as they sometimes produce incorrect information about the article and miss key points. They are also more difficult to explain for business buy-in and adoption. 

### Repo Contents
_Scripts_ in Run Order:
1. cnn_data: unzip and create dictionary from cnn data
2. exploratory_analysis: prepare raw data for analysis & perform exploratory analysis of articles and summaries.
3. compress_fasttext: compress FastText embeddings into a smaller object to fit RAM constraints at the cost of some accuracy
4. extractive_summarization_train: Train 3 different extractive summarization models (Baseline TF-IDF, TextRank, LSA) on a variety of configurations using a small subset of the data, select the best configuration for each evaluation metric for each model, and retrain on larger subset of data. Uses functions created in extractive_summarization.
5. abstractive_summarization: Apply the pre-trained T5 model to our data with a variety of configurations for decoding parameters using a small subset of the data, select the best configuration for each evaluation metric for each model, and re-decode a larger subset of the data. 
6. compare_models: for the best configurations of models, calculate the p-values of the difference between model's evaluation metrics and perform exploratory analysis of best models.


_Visualization_ folder: html versions of bokeh visualizations created in exploratory_analysis and compare_extractive_models

_Report_: FinalReportTruebenbach 
