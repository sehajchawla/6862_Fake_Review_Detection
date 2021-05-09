## Directory Contents

This `1_yelp` directory contains the following:
* `1_parsing_yelp.ipynb`: parses and stores the raw data for yelp into a easily readable `.csv` format.
* `2_exploration_yelp.ipynb`: does some initial EDA for the yelp data to understand its contents and familiarise the format.
* `3_feature_extraction_yelp.ipynb`: does some joins to add metadata to the reviews which we need for the distribution splits later.
* `4_initial_text_modelling_yelp.ipynb`: initial modelling done using LSTMs and FFNNs, which were far outperformed by the pretrained transformer models later
* `5_parsing_for_T5_yelp.ipynb`: parses and stores the data for the reviews in a format that is compliant for the T5 model (different from the BERT format requirement).

## Data

The data that is being referred to on the notebooks is all in the following Google Drive folder that should be accessible with any `mit.edu` email: `https://drive.google.com/drive/folders/1RA5QyeQpAJhWrYIxoYFBdTq_RQXsk7TZ?usp=sharing`.

## Contact

For any questions, email any of the following:
* Sehaj Chawla (Harvard University): sehajchawla@g.harvard.edu
* Eduardo Boratto (MIT Sloan): eboratto@mit.edu
* Joanne Im (MIT Sloan): joanneim@mit.edu
