# Anomaly Detection in Network Intrusion Data using Unsupervised Learning
This project implements an unsupervised anomaly detection system for network intrusion data using the Isolation Forest algorithm.

📊 Dataset
Name: UNSW-NB15 Dataset

Source: UNSW Canberra Cybersecurity (Requires download of training and testing CSV files)

Features Used: All network traffic features (42 columns after dropping id, label, and attack_cat for unsupervised training).

🔧 Technologies Used
Python

Jupyter Notebook

Libraries:

pandas for data manipulation

numpy for numerical operations

matplotlib for plotting

seaborn for statistical data visualization

scikit-learn for machine learning algorithms (specifically IsolationForest, LabelEncoder, StandardScaler)

📈 Methodology
Data Loading & Combination: Load UNSW_NB15_training-set.csv and UNSW_NB15_testing-set.csv and combine them into a single DataFrame.

Data Preprocessing:

Handle missing values (fill with 0 for numerical, 'unknown' for categorical).

Drop non-feature columns (id, label, attack_cat) from the training data.

Encode categorical features using LabelEncoder.

Scale numerical features using StandardScaler.

Isolation Forest Model Implementation:

Initialize and train the IsolationForest model on the preprocessed, unlabeled data.

The contamination parameter (set to 0.01) estimates the proportion of anomalies in the dataset.

Anomaly Score & Label Prediction:

Generate anomaly scores using model.decision_function().

Predict anomaly labels (-1 for anomaly, 1 for normal) using model.predict().

Analysis of Detected Anomalies:

Analyze the distribution of anomaly labels (-1 vs 1).

Perform a qualitative assessment by mapping detected anomalies back to their original attack_cat labels to see which known attack types were flagged.

Visualization:

Histogram of anomaly scores, showing the calculated anomaly threshold.

Scatter plot of key features (sbytes vs dbytes) highlighting normal vs. anomalous points, using symmetric logarithmic scales for better visualization of wide-ranging values.

📌 Results
Successfully identified anomalous network connections within the UNSW-NB15 dataset.

The model detected a significant number of known attack types (e.g., Exploits, Fuzzers, DoS) as anomalies, validating its effectiveness.

Notably, the model also flagged "Normal" instances as anomalous, which could represent rare legitimate behaviors or potentially novel, unseen threats.

Visualizations provide clear insights into the distribution of anomaly scores and the separation of anomalous points in feature space.

The project demonstrates the practical application of unsupervised learning for enhancing network security threat intelligence.

📤 Output
All Python code, analysis steps, and generated visualizations are contained within the Jupyter Notebook file (e.g., major_project-checkpoint.ipynb or your renamed version like Network_Anomaly_Detection_Project.ipynb).

📜 License
This project is licensed for academic and learning purposes only.
