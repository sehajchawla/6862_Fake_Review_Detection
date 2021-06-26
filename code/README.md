## Directory Contents

This `code` directory contains the following:
* `1_preprocess`: parses and preprocesses are data sets to make them compliant with our pretrained transformer models (3 instances of BERT and 1 of T5).
* `2_baseline`: creates and evaluates baseline models that train and test on the same distribution (but test on OOD), in order to establish baselines that we can compare our distribution shift results with.
* `3_distribution_shift`: contains 4 types of distribution shifts (`1_industry`, `2_time`, `3_product`, and `4_sentiment`) and the results for our analysis in each. 
* `4_finetune_shift`: contains 4 types of distribution shifts (`1_industry`, `2_time`, `3_product`, and `4_sentiment`) and the results for our analysis in each after taking 20% of the new distribution to retrain the final layer of model trained on the original distribution. 

## Data

The data that is being referred to on the notebooks is all in the following Google Drive folder that should be accessible with any `mit.edu` email: `https://drive.google.com/drive/folders/1RA5QyeQpAJhWrYIxoYFBdTq_RQXsk7TZ?usp=sharing`.

## Contact

For any questions, email any of the following:
* Sehaj Chawla (Harvard University): sehajchawla@g.harvard.edu
* Eduardo Boratto (MIT Sloan): eboratto@mit.edu
* Joanne Im (MIT Sloan): joanneim@mit.edu
