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
5. 
* `code/notebook_5a_text_modelling_with_BERT_large.ipynb`: This notebook is similar to notebook 4, but uses state of the art contextualised text models BERT (large) - more specifically `bert_uncased_L-12_H-768_A-12`, to predict the fake label based on the text only. The BERT embeddings are fed into a Dense model with dropouts for regularization. This model performs much better than LSTM's and FFNN's. 
* `code/notebook_5b_text_modelling_with_BERT_small.ipynb`: Here we use the contextualised text model BERT (small) - more specifically `bert_uncased_L-4_H-256_A-4`, to predict the fake label based on the text only. The BERT embeddings are fed into a Dense model with dropouts for regularization. This model is lighter than the larger version of BERT, and is comparable in out of sample performance.
* `code/notebook_5c_text_modelling_with_mobile_BERT.ipynb`: This notebook is similar to notebook 4, but uses state of the art text models BERT (large) - more specifically `uncased_L-24_H-128_B-512_A-4_F-4_OPT`, to predict the fake label based on the text only. The BERT embeddings are fed into a Dense model with dropouts for regularization. This model performs the best on the test set (although just marginally), but the big advantage is that it is very light, and perhaps is performing well for that reason, since it is not overcomplicating the task.
