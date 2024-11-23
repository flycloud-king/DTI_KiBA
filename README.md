# DTI_KiBA: Predicting drug-target binding affinity with KiBA dataset

The code is implemented with Python 3.10.12, as it is compatible with library "ProtEnc". Other libraries for protein sequence embedding (such as "protvec") were tested but none worked, also none of libaries worked on Python 3.12.3

The input data seems to be an extended dataset of the original KiBA dataset, with many KiBA score estimated. Due to the large size of the data set, two subsets were used for model building. However, the subset with all KiBA score measured (not estimated), always got the memory error during sequence embedding step, this the model was only built on the subset with highly interacting proteins and compounds pairs.

Two types of models were trained: RandomForest and XGBoost. A sinple approach with train test splitting, then a single model is build on train data and tested on test data. Both models show signs of over-fitting and XBGoost was more so. The nested cross-validation approach was tried to overcome bias and overfitting problem but it took forever to finish.

The test section is the at the end in Section 5. Assuming the test file is in the same format as the input file. Then went through several steps to generate the predictions


