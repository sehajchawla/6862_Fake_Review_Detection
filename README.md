# Investigating Distribution Shifts in Review Classification

## Abstract

This work quantifies the extent of the degradation of review classification accuracy when state of the art transformer models are subjected to distribution shifts, while offering a solution to decrease this degradation significantly. We find that the extent of degradation depends primarily on the independent variable chosen, around which the shift is created. Time and sentiment shifts show 0-10\% drops in accuracy; whereas shifts between industry and product sectors show 20-40\% drops in accuracy. We provide ablation experiments with different Transformer architectures, such as BERT and T5, and study their relationship with this degradation. We also suggest a solution that reuses the base of the model trained on one distribution, in addition to fine-tuning the final dense layer in the model to support the new distribution that is seen once the model is deployed. This solution uses just 100-300 samples from the unseen distribution, while decreasing the accuracy drop in the industry and product shifts by half.

## Code Structure

The code structure for our project is as follows:
The `code` directory contains the notebooks that we worked on, and is structured as per the "steps" section in our report. i.e. it contains the following subdirectories:
* `1_preprocess`: parses and preprocesses our data sets to make them compliant with our pretrained transformer models (3 instances of BERT and 1 of T5).
* `2_baseline`: creates and evaluates baseline models that train and test on the same distribution (but test on OOD), in order to establish baselines that we can compare our distribution shift results with.
* `3_distribution_shift`: contains 4 types of distribution shifts (`1_industry`, `2_time`, `3_product`, and `4_sentiment`) and the results for our analysis in each. 
* `4_finetune_shift`: contains 4 types of distribution shifts (`1_industry`, `2_time`, `3_product`, and `4_sentiment`) and the results for our analysis in each, where we retrain the final layer of a model trained on one distribution with 20% samples from the other distribution. 

Most of the work seen in the "results" section of our report will be found in the directories `3_distribution_shift` and `4_finetune_shift`.

## Data

The data that is being referred to on the notebooks is all in the following Google Drive folder that should be accessible with any `mit.edu` email: `https://drive.google.com/drive/folders/1RA5QyeQpAJhWrYIxoYFBdTq_RQXsk7TZ?usp=sharing`.

## Contact

For any questions, email any of the following:
* Sehaj Chawla (Harvard University): sehajchawla@g.harvard.edu
* Eduardo Boratto (MIT Sloan): eboratto@mit.edu
* Joanne Im (MIT Sloan): joanneim@mit.edu
