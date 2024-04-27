# Design Overview
Our proposed solution leverages supervised machine learning, focusing particularly on Naive Bayes and neural networks, to identify DDoS attacks. Machine learning offers adaptability to novel datasets, making it an ideal tool for accurately predicting DDoS attacks. To ensure robust model performance, we will employ 10-fold cross-validation. This technique divides the labeled dataset into ten equal-sized folds, with 90% of the data used for training in each iteration and the remaining fold for testing. This iterative process ensures that each data point is tested exactly once. Aggregating performance metrics across all folds provides a reliable estimate of the model's generalization capability.

## How It Works
During the training process, we analyze network traffic data from a pre-existing dataset, extracting relevant features such as packet size, protocol type, and flow duration. These features serve as input variables for the machine learning models, which aim to differentiate between normal and anomalous traffic patterns via binary classification. Once trained, the models can effectively identify suspicious activities within the network.

### Evaluation

#### Dataset
For our evaluation, we will utilize two publicly available datasets containing labeled instances of both normal network traffic and DDoS attacks. 
The first dataset (OpenML), sourced from the ACM KDD Cup 1999, provides a comprehensive set of data for network intrusion detection. It includes various types of attacks, such as denial-of-service (DOS), unauthorized access attempts (R2L and U2R), and probing activities. The dataset comprises features extracted from TCP connections, including protocol type, service, packet size, and more.

The second dataset (IDS 2017 | Datasets | Research | Canadian Institute for Cybersecurity | UNB), CICIDS2017, offers a more recent and comprehensive collection of network flow data. It covers a diverse range of attacks, including brute force, DoS/DDoS, infiltration, and botnet activities. This dataset includes features extracted from network traffic, captured from a complete network configuration with various operating systems and protocols.

In addition to our two main datasets, we'll reserve a third dataset specifically for validation. This step is crucial for rigorously testing our model's accuracy and generalization abilities. By using a separate validation set, we guard against overfitting and ensure our model's reliability and performance on unseen data.

#### Evaluation Metrics
To assess the performance of our machine learning models, we will employ Receiver Operating Characteristic (ROC) curves and Area Under the Curve (AUC) scores. These metrics provide valuable insights into the trade-off between true positive and false positive rates, enabling us to gauge the effectiveness of our detection algorithms across different thresholds. By analyzing ROC curves and calculating AUC scores, we can evaluate the models' ability to discriminate between normal and malicious network traffic accurately.

By leveraging these datasets and evaluation metrics, we aim to validate the efficacy of our proposed machine learning approach for DDoS attack detection and contribute to advancing the field of network security.
