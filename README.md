# intel-image-classification-simple-cnn
intel-image-classification-simple-cnn

Overview

This project is a computer vision practice project using the Intel Image Classification dataset from Kaggle.

The goal was to build a Simple CNN, identify model weaknesses using class-level recall and confusion matrix, and compare different tuning methods.

Main question:

Does adding BatchNorm or Dropout improve CNN performance?

Dataset

Dataset: Intel Image Classification
Source: Kaggle puneet6060/intel-image-classification

The dataset contains 6 natural scene classes:

buildings
forest
glacier
mountain
sea
street

Task: Multi-class image classification

Model Versions
Version	Tuning	Purpose
v1 Baseline	None	Basic CNN performance check
v2 BN	BatchNorm2d	Stabilize training
v3 Dropout	Dropout	Reduce overfitting
v4 BN + Dropout	BatchNorm2d + Dropout	Combine both tuning methods
Results
Version	Accuracy (%)	Glacier Recall	Mountain Recall	Buildings Recall	Weakest Class
v1 Baseline	80.13	0.7649	0.7505	0.8101	mountain
v2 BN	85.33	0.7830	0.8000	0.7368	buildings
v3 Dropout	82.07	0.7722	0.7848	0.7391	buildings
v4 BN + Dropout	83.83	0.8282	0.7714	0.7483	buildings
Key Findings
The baseline CNN achieved 80.13% accuracy.
The weakest class in the baseline model was mountain.
Adding BatchNorm2d gave the best result with 85.33% accuracy.
Dropout improved the baseline model, but it did not outperform BatchNorm.
BN + Dropout improved glacier recall, but overall accuracy was lower than BN alone.
Conclusion

The best model was v2 BatchNorm, with the highest overall accuracy and improved mountain recall.

This experiment showed that CNN tuning is not a fixed recipe.
Adding more techniques does not always guarantee better performance.

For this dataset, BatchNorm alone worked better than Dropout or BN + Dropout.

What I Learned
How to build a Simple CNN with PyTorch
How to compare multiple CNN versions
How BatchNorm and Dropout affect model performance
Why class-level recall matters
How to identify model weakness using recall and confusion matrix
Tools Used
Python
PyTorch
Torchvision
Scikit-learn
Matplotlib
Kaggle Notebook
Next Step

This project will be used as a foundation for healthcare computer vision projects, such as Chest X-ray tuberculosis classification.
