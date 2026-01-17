# Linear ensemble model with winner-takes-all aggregation strategy for improved small data classification
In this repository implemented an ensemble of linear machine learning algorithms that constructs an ensemble of linear regressors, where a separate binarized regressor is trained for each class. After normalizing the output of each weak regressor, the final prediction is obtained using a winner-takes-all aggregation strategy. The method is evaluated on 3 real medical datasets collected in Ukrainian hospitals, which differ both in terms of the number of features and in terms of subject specificity.
# Training pipeline

<p align="center"><img width="610" height="670" alt="image" src="https://github.com/user-attachments/assets/5a975373-245d-40ea-bc37-3a6e33ec4c05" /></p>

The proposed ensemble model is trained sequentially on the training data, which is first split from the test set. For each class, a one-vs-all subset is created with binary targets, producing as many subsets as classes. Each subset undergoes feature-wise and sample-wise normalization to ensure consistent scaling and robustness. Class-specific regressors are then trained on these subsets, with each model specializing in one class. During training, the minimum and maximum predictions of each regressor are recorded for later aggregation and decision-making. This approach efficiently trains a robust ensemble of lightweight regressors while handling class imbalance and feature scaling differences.

# Inference

<p align="center"><img width="621" height="495" alt="image" src="https://github.com/user-attachments/assets/2a658ce3-422a-4c01-b86b-ef779c5d423f" /></p>

The ensemble application algorithm works by first normalizing the input vector, then passing it through each of the pre-trained regressors. Each regressor’s output is normalized using stored min–max values to remove scale dependence. The final class is determined using a “winner-takes-all” approach, selecting the class with the highest normalized prediction. This process ensures robustness and generalizability to new data.
 
# Dataset

For testing and validation of the developed method, modeling was conducted on an extremely small
dataset collected by specialists from the Department of Anesthesiology and Intensive Care at
the Kharkiv City Clinical Hospital of Emergency and Urgent Medical Care. The task consists of predicting mortality in patients with polytrauma based on 56
clinical and laboratory tests to assess the risk of death, optimize triage in intensive care settings,
monitor treatment effectiveness, and support medical decision-making.
The dataset contains 73 samples of male patients hospitalized due to polytrauma. It includes 56
independent attributes covering a variety of clinical and laboratory indicators. The dependent variable
is mortality, labeled as 1 (fatal case) and 0 (survival). Out of the total 73 cases, 31 were fatal, and 42
survived.


# Results

To quantitatively evaluate the performance of the proposed ensemble algorithms, a series of experiments were conducted using various linear machine learning methods as weak predictors within the developed ensemble framework:

- **Algorithm 1** – proposed ensemble via SGTM neural-like structure  
- **Algorithm 2** – proposed ensemble via SVM with linear kernel  
- **Algorithm 3** – proposed ensemble via Ridge regression
<p align="center"><img width="521" height="673" alt="image" src="https://github.com/user-attachments/assets/8f1f56e4-5cd0-474f-84db-103681207e3d" /></p>
