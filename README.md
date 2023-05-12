# Medical Imaging - MRI classification and vessel segmentation on retinal fundus images

This is my repository containing code for classifying brain MRI scans into people with Alzheimer's disease (AD) and cognitively normal (CN) controls. In addition to the AD classification task, the repository also includes code for performing vessel segmentation in retinal fundus images.


### MRI Classification

In the first section, I load and preprocess the data from the MRI scans dataset. I compute means and standard deviations for the amyloid protein levels of CN and AD groups and derive a decision boundary using Gaussian distribution assumptions. I also train a linear regression model to separate CN from Dementia subjects and generate a scatter plot with the decision boundary.

In the second section, I implement three classification algorithms: **Rosenblatt's Perceptron**, **Logistic Regression** using gradient descent, and a **Linear Classifier** using Hinge Loss and L2 regularization. I load datasets 'sim_data.csv' and 'sim_data_nonsep.csv' and train models using these algorithms. I also generate scatter plots with the decision boundaries for each model.

In the third section, I discuss the approach of using Ridge Regression for the classification task and evaluate its performance on the dataset of MRI scans.

### Vessel segmentation
In the fourth section, I worked on a segmentation task using fundus images and their corresponding masks. I randomly sampled 50 patches of size 7x7 from the training images and used scikit-learn to train a Support Vector Classifier (SVC) to segment vessels. I optimized the kernel choice (RBF or polynomial with degree 3) and the cost parameter (C in the range 0.01 to 100) using cross-validation, and measured the model's performance using the Area Under the ROC Curve (roc_auc). I plotted the performance of both kernels depending on the C parameter, and changed the C parameter when the training time became too long.

Based on the results, I selected the best model parameters and made predictions on the 10 images in the validation dataset. I computed the DICE coefficient and roc_auc for each image, and displayed the original image, ground truth, and segmentations for each of the 10 images. I also provided the average DICE coefficient and roc_auc for the dataset.
