# 6862 Fake Review Detection

The code structure for our project so far is as follows:
* The `code` directory contains the notebooks that we worked on.
* Each of the notebooks takes in some data and saves the updated version of the data after processing/modelling on top of the input data.

The data that is being referred to on the notebooks is all in the following Google Drive folder that should be accessible with any `mit.edu` email: `https://drive.google.com/drive/folders/1RA5QyeQpAJhWrYIxoYFBdTq_RQXsk7TZ?usp=sharing`.

Please refer to the above link for all the data files mentioned in the details below.

Now, to describe what each notebook does we have:
1. `code/notebook_1_data_parsing.ipynb`: This notebook takes in the raw data that we had (files: `amazon_grocery_gourmet.json.gz`, `amazon_prime_pantry.json.gz`, and `yelp_all`) and parses it into a format that is easy to work (files: `amazon_grocery_gourmet.csv`, `amazon_prime_pantry.csv`, and `yelp_all.csv` respectively).
2. 
* `code/notebook_2a_yelp_exploration.ipynb`: This notebook performs some preliminary exploration just to get familiar with the csv file (`yelp_all.csv`) and the raw features we have to work with. 
* `code/notebook_2b_amazon_exploration.ipynb`: This notebook performs some preliminary exploration just to get familiar with the csv file (`amazon_grocery_gourmet.csv` and `amazon_prime_pantry.csv`) and the raw features we have to work with.
3. `code/notebook_3_processing_and_feature_extraction.ipynb`: This notebook incorporates some more of the raw data files we had from the yelp data that included metadata for each review. In here, we first join the metadata with the review text, and then create some more features such as word count and sentiment analysis. This is then finally saved in `yelp_processed_metadata.csv`.
4. `code/notebook_4_text_modelling.ipynb`: This notebook only uses the reviewText field to first create embeddings for the text and then model the `fakeLabel` attribute using `Feed Forward Neural Network` and `Bidirectional LSTM`. This current version of the notebook only has these two processes, but the third model `pretrained BERT` is currently still being trained so that better performance can be expected from more meaningful embeddings. This notebook will, therefore, soon be updated to incorporate `BERT` (Bidirectional Encoder Representations from Transformers). After the modelling, this notebook predicts the values for each review and stores it in the file named `yelp_with_text_preds.csv`.
5. `code/notebook_5_metadata_and_performance.ipynb`: This notebook takes the prediction probabilities from `notebook_4_text_modelling` (from the file  `yelp_with_text_preds.csv`), and combines them with the metadata from `notebook_3_processing_and_feature_extraction` (from the file `yelp_processed_metadata.csv`). It then, finally, does preliminary modelling using `Logistic Regression`, `Random Forests Classifier`, and `MLP Classifier`. It also looks at the confusion matrix and the f1 score for these models. More models and more hyperparameter tuning will be done with in this notebook in the future, perhaps using cross validation.

