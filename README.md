# IoT Network Anomaly Detection


# Overview of Project
This study proposes a machine learning model specifically tailored for the classification of network packets within IoT environments as either normal or malicious. The process begins with the IoT Environment Dataset, which comprises network traffic data captured from various IoT setups and stored in PCAP files, enabling detailed analysis of network interactions. The dataset undergoes a preliminary split, distributed as 70% for training, 15% for validation, and 15% for testing. This distribution is designed to optimize the training phase while allowing for thorough validation and unbiased evaluation during testing. Multiple machine learning algorithms are employed to handle the classification tasks, including Logistic Regression, Naive Bayes, Decision Trees, Random Forest, Multi-Layer Perceptron, Support VectorMachines and XG Boost. Each model is chosen based on its ability to address specific challenges posed by the high-dimensional and complex nature of IoT network traffic data. 
During the training and validation phases, the models are rigorously tested for their effectiveness in classifying the traffic accurately. If the outcomes from the validation phase are deemed unsatisfactory, adjustments are made in model configurations, training strategies, or even algorithm selection to enhance performance. Successful models that pass this phase are then subjected to the final test using the designated 15% of the data reserved for testing. 
The final evaluation of the models is based on critical metrics such as accuracy, precision, recall, and F1-score, among others. These metrics help determine the most effective model for deployment in real-world scenarios. Should a model exhibit acceptable performance metrics, it proceeds to the deployment phase where it can be integrated into existing IoT infrastructures. This integration involves utilizing multi-core CPU systems to handle the computational demands, ensuring that the model functions efficiently in real-time environments. 
Our proposed model not only identifies and classifies potential threats but also offers a scalable and efficient solution suitable for different IoT environments. By continuously refining the models through re-training and updating with new data, the system maintains high accuracy and relevance in detecting and mitigating malicious activities within IoT networks. The dynamic nature of this model, coupled with its ability to adapt to various computational and resource constraints, makes it an ideal solution for diverse IoT security needs, balancing between performance and cost-effectiveness. 


# Preprocessing and Transformation
Given the high number of continuous features available, selecting the correct set of features for our modeling is of utmost importance.  For feature selection, several strategies were employed: 

**Dropping timestamp-related columns:** As no significant trend was observed, timestamp-related columns were excluded. 

**Scaling numerical features and analyzing outliers:** All numerical features were scaled, and outliers were analyzed to identify patterns.

**Dropping non-impactful columns:** Columns like source and destination IP addresses and port numbers were dropped as they did not significantly impact the modeling. 

**Removing UDP protocol data:** Due to minimal counts, UDP protocol data was removed, followed by dropping the protocol-related feature. 

**Analyzing correlation among features:** A correlation matrix was used to analyze and drop highly correlated features to reduce redundancy. 

The Shapiro-Wilk test was employed to validate whether each feature follows a normal distribution. Approximately 45% of the features exhibited a normal distribution. Initial modeling will commence with this set of features, with additional features potentially included later to improve accuracy. Scaling may be necessary to normalize the data for these additional columns. These steps ensure that the selected features are most relevant for detecting anomalies in IoT network traffic, thereby enhancing the model’s accuracy and performance.This detailed analysis and feature selection process provide a solid foundation for building robust machine learning models for anomaly detection in IoT environments. 
