## Links

- [GitHub Repo](https://github.com/drosophominin/PH582-ML-Final_Project)
- [Pre-Proposal](https://docs.google.com/document/d/1BtWiQr21Crni3SstO6BSUOCDgrLlvCOQu6uzhpSgEAw/edit#)

We would very much like to set up a time and meet to discuss what would be our best course of action.

## Estimating When a Package Will be Delivered to a Given Gddress
- We plan to estimate when a package will be delivered given the carrier, current time of “Out for Delivery”, and address to which it is delivering to.
- When packages are sent out for delivery, the time that they actually get delivered depends on:
	- Route
	- Delivery driver
	- Carrier
	- Size (affects location of delivery (mailbox/door), affects position in linear route)
	- Address (position in linear route)
- Data we need:
	- Name, as an identifier of location.
	- Courier
	- Mailbox delivery
	- Date of “Out for Delivery”
	- Time of “Out for Delivery”
	- Date of “Delivered”
	- Time of “Delivered”
- ADV:
	- Straightforward to implement
	- Useful (at least for CPR)
- DisADV
	- Data is going to be limited unless we expand our acquisition efforts soon

## Annotating Regulatory Regions and Classifying Promoters
- To classify whether certain regulatory regions of genes (potential promoters) are actually being used to initiate transcription
- To be able to expand this to ML algorithms instead of the current state of sticking to HMMs and MCMCs.
- Would need the information found in `/pre_proposal/tss_format.json` for all scaffolds in all assemblies.
	- Some of this information would only be needed in our training assembly (`dm6`), and will be commented for that line
	- More data types could also be added as we start to extract the data, and as we see a need
	- We could also format this as a 2D array if it would be easier for the ML algorithms to parse
- ADV:
	- Super useful, needed for TSS and regulatory network annotations
	- Would be used extensively, and if published, would be cited a decent amount
	- Completely novel approach to classifying TSS
	- Have all data for 27 assemblies as BigBed format already.
- DISADV:
	- Would take a lot of computational hours to parse through dataset
	- Would require an initial effort to classify and extract TSS regions from assemblies
	- Do not have assembly data for `dm6`, but will be easy to obtain

There are further disadvantages with this project, and they are going to primarily at the scale at which we would need to operate.
- We would need a rather large dataset to be effective at prediction. This dataset would have to be obtained computationally, and coding that extraction process is going to take a lot of man hours.
- We would also need to incorporate Hi-C data (structure-based), and I (CPR) is still learning how to parse that data, and it will take a lot of time.
- Current TSS predictors are heavily relying on Hidden Markov Models (HMMs) for accuracy, and they have current prediction rate at 30-40%.
	- This is not good, and we would need to incorporate more data/a broader set to effectively annotate TSSs/regulatory regions.
- Further optimizations would have to be made for whole-genome data, which we would need to effectively classify TSSs/regulatory regions.

The advantages of using this study is still there, but due to lack of time and current lack of skillset, we would advise not going forward with this as of this time.
I (CPR) am reading into this more.

- Sloutskin, A., et al. (2015). "ElemeNT: a computational tool for detecting core promoter elements." Transcription 6(3): 41-50.
- Pedersen, A. G., et al. (1999). "The biology of eukaryotic promoter prediction—a review." Computers & Chemistry 23(3): 191-207.

## Predicting breast cancer using "Breast cancer Wisconsin (Diagnostic) dataset".
Tumor cells are classified as either Benign (B) or Malignant (M). B implies that the cells are non-cancerous and lack the potential to invade neighboring tissues. M refers to the tumor cells that enter an uncontrolled growth phase and destroy the tissues.

Features of breast mass were computed using a digitized image of Fine needle aspirate (FNA) and these describe the characteristics of the cell nuclei present in the image. The dataset with all the attribute information is available on UCI Machine Learning Repository. https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29

The main goal here is to use the available data to predict whether the cells are malign or benign.
We want to implement various classifiers and deep learning for predicting the class of the cells and compare their accuracies.

- ADV:
	- Fundamental goal of cancer biology is to early detect and predict. Application of Machine Learning techniques on these systems will help the cancer researchers 	make robust cancer predictions and prognosis.
- DISADV:
	- Available literature in the field of "ML and cancer prediction" is limited.
	- The above mentioned dataset has 569 instances. There definitely is a need to obtain a bigger dataset to make robust predictions for these kinds of systems whose results could have a huge impact on one's life.
