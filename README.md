# Investigating Distribution Shifts in Review Classification

## Abstract

Online, user generated reviews drive and inform consumer choice. Their continuingusefulness,  however,  depends  on  trust  that  these  reviews  are  truthful,  whichhas motivated the development of algorithms that detect fake review based onreview text.  The dearth of publicly available training datasets of reviews withfake/real  labels,  however,  raises  concerns  about  the  generalizability  of  thesealgorithms. We test this directly by exploring the effects of distribution shifts (withrespect to time, industry type, product type, and sentiment) on the performanceof four pre-trained and fine-tuned transformer models. The first three models areneural nets built on top of three pre-trained instances of BERT (large, small, andmobile), which generate contextualised embedding of review text in a way that ismechanically independent from our training dataset. Our fourth model, is the smallT5 transformer.

## Code Structure

The code structure for our project is as follows:
The `code` directory contains the notebooks that we worked on, and is structured as per the "steps" section in our report. i.e. it contains the following subdirectories:
* `1_preprocess`: parses and preprocesses our data sets to make them compliant with our pretrained transformer models (3 instances of BERT and 1 of T5).
* `2_baseline`: creates and evaluates baseline models that train and test on the same distribution (but test on OOD), in order to establish baselines that we can compare our distribution shift results with.
* `3_distribution_shift`: contains 4 types of distribution shifts (`1_industry`, `2_time`, `3_product`, and `4_sentiment`) and the results for our analysis in each. 
* `4_finetune_shift`: contains 4 types of distribution shifts (`1_industry`, `2_time`, `3_product`, and `4_sentiment`) and the results for our analysis in each, where we retrain the final layer of a model trained on one distribution with 20% samples from the other distribution. 

There are `README` files in each folder describing the purposes and contents of the folder. This is done to make it easy to navigate through them, but most of the work seen in the "results" section of our report will be found in the directories `3_distribution_shift` and `4_finetune_shift`.

## Data

The data that is being referred to on the notebooks is all in the following Google Drive folder that should be accessible with any `mit.edu` email: `https://drive.google.com/drive/folders/1RA5QyeQpAJhWrYIxoYFBdTq_RQXsk7TZ?usp=sharing`.

## Contact

For any questions, email any of the following:
* Sehaj Chawla (Harvard University): sehajchawla@g.harvard.edu
* Eduardo Boratto (MIT Sloan): eboratto@mit.edu
* Joanne Im (MIT Sloan): joanneim@mit.edu
