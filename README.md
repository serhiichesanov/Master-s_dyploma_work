# Linear ensemble model with winner-takes-all aggregation strategy for improved small data classification
In this repository implemented an ensemble of linear machine learning algorithms that constructs an ensemble of linear regressors, where a separate binarized regressor is trained for each class. After normalizing the output of each weak regressor, the final prediction is obtained using a winner-takes-all aggregation strategy. The method is evaluated on a medical dataset containing records from 73 patients with polytrauma.
# Training pipeline

<img width="610" height="670" alt="image" src="https://github.com/user-attachments/assets/5a975373-245d-40ea-bc37-3a6e33ec4c05" />

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
