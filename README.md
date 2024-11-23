# DTI_KiBA
Model for drug-target interaction prediction based on KiBA dataset

Started with python 3.12.3, and none of the libraries for protein sequence embedding worked. After some exploration, the one worked is python 3.10.12, and only one library "ProtEnc" worked. The "protvec" library, which may be more popular, didn't work for me so far.

I tried to create two subsets for model building, but the subset with all KiBA score measured (not estimated), always get the memory error during sequence embedding step, so I only got to build the model on the subset with highly interacting proteins and compounds pairs.

Two types of models were trained: RandomForest and XGBoost. A single approach with train test splitting, then a single model is build on train data and tested on tested. Both models show signs of over-fitting and XBGoost more so. Then I tried the nested cross-validation approach, and it tool forever to run.

The test section is the at the end in Section 5. Assuming the test file is in the same format as the input file. Then went through several steps to generate the predictions


