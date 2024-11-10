
Machine Learning
a study field give computers ability to learn without explicitly programmed

Types of machine learning

1. Supervised Learning
2. Unsupervised Learning
3. Enforcement Learning


## 1. Supervised Learning

Learns from begin given "right answers"

### type of supervised learning

##### Regression
- predict a number
- infinitely many possible outputs
- give every item a value



##### Classification
- we call output (class - category)
- predict categories
- Small number of possible outputs
- Classification algorithms can also have more than two possible output categories. In supervised learning, inputs can include multiple variables, and the learning algorithm finds a boundary that separates different categories.

For example, in breast cancer detection, a classification problem, the goal is to determine if a tumor is benign or malignant.



## 2. Unsupervised Learning

Unsupervised learning is a type of machine learning where we are given data without any labels or categories. Instead of trying to find specific answers or predictions, the goal of unsupervised learning **is to discover patterns, structures, or interesting information within the data.**

The key idea is that unsupervised learning allows the algorithm to find its own patterns and structures in the data without being told what to look for. It's like giving the algorithm a puzzle and letting it figure out how the pieces fit together.

For example, the algorithm might find that there are two distinct groups of patients based on their tumor sizes and ages. This is called clustering, and it can be used in various applications like grouping news articles or segmenting customers based on their preferences.
### type of unsupervised learning

#### Clustering
Clustering is a technique in unsupervised learning where we group similar data points together based on their characteristics or features. The goal of clustering is to find patterns or structures within the data without any predefined categories or labels.

In clustering, the algorithm examines the data and identifies groups or clusters that share similar properties. These clusters can be based on various factors such as distance, similarity, or density. The algorithm assigns each data point to a cluster based on its similarity to other data points in that cluster.

Clustering is commonly used in various fields and applications. For example, in 
- customer segmentation, clustering can help identify groups of customers with similar preferences or behaviors. In 
- image analysis, clustering can be used to group similar images together. 
- Clustering is also used in recommendation systems, anomaly detection, and many other areas where finding patterns or grouping similar data is important.

#### Anomaly detection
Anomaly Detection: Anomaly detection is another type of unsupervised learning that focuses on identifying unusual (events) or abnormal data points in a dataset

The algorithm learns the normal patterns or behaviors from the majority of the data and then flags any data points that deviate significantly from those patterns

 This can be useful in:
 - detecting fraudulent transactions
 - network intrusions, or any other unusual events.


#### Dimensionality Reduction

Dimensionality reduction is the process of reducing the number of features or variables in a dataset while preserving as much relevant information as possible.

This is particularly useful when dealing with high-dimensional data, where the number of features is large. By reducing the dimensionality, we can simplify the data

representation, remove noise, and improve computational efficiency. Principal Component Analysis (PCA) is a popular technique for dimensionality reduction.