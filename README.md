# Adultincome-prediction-using-DecisionTreefromscratch
Datamining project that determines the adult income using python decision tree implementation from scratch.
DESIGN DECISIONS TAKEN WITH THE DATA:
PREPROCESSING:
	Once data exploration has been done, there are few pre-processing steps taken care before segregating them into training and testing dataset.
	Initially there were column names to be assigned for more readability and processing.
	Null and duplicate values were checked and it was noted that there was no null values. Hence the dropping of the duplicate values were done. 
	Invalid values found in the native-country column (?) were replaced by Unknowncountry.
	Conversion of categorical features to numerical features was done for enhanced performance of the overall model.
	To achieve normalization the numerical columns were modified using StandardScalar library.
	The dataset was divided into feature matrix and target vector for interpretation by assigning the income column as the target vector.
	Value of income is mapped by >50k as "1" and <50k as "0" for easier interpretation in decision tree
	The dataset was split to training and testing dataset in ratio 80:20.

SIMILARITY METRIC CHOSEN: 
	Information gain is used to determine which feature to split on and the threshold to use for the split. The algorithm tries to maximize the information gain, which is defined as the difference between the entropy of the parent node & weighted average of the entropy of the child nodes.

STOPPING CRITERION:
	Minimum samples split: A node will not be split if it contains fewer samples than the specified min_samples_split.
	Maximum depth: The tree will not grow beyond the specified max_depth depth.
	Number of features: The number of features considered for the split at each node is limited to the specified n_features. If not specified by the user, it defaults to the total number of features.

This model created defines a Decision Tree Classifier algorithm from scratch without using any external libraries. The algorithm is defined as a class with various sub-functions to grow the tree, determine the best split, calculate entropy and information gain, and assign leaf node values. Apart from these main function there is also an array of helper functions that facilitate these calculations. The train-model function takes in a set of training data and labels, and builds the decision tree based on the provided hyper-parameters such as the minimum number of samples required to split a node, the maximum depth of the tree, and the number of features to consider when looking for the best split. It is built in such a way that the model hyper-parameters if not prescribed by the user is targeted to take in what is provisioned within the algorithm itself.
The decision tree is a model that creates a tree diagram model to identify the subcategory branches by considering the split for the feature at any particular point. The subtrees are built unless the stopping point is met where the leaf nodes are determined by the tree. The algorithm does this using a recursive approach. The recursion takes place by aiming to grow the tree by creating child nodes until the stopping criterion are faced such as reaching the maximum depth, having only one label in the node, or having too few samples to split. The algorithm also implements randomness by randomly selecting a subset of features to consider for each split. 
Once the tree is built, and the model is trained, the predict function can be used to classify new instances by traversing the tree and assigning the leaf node values for the prediction dataset which is also known as the testing dataset.

Performance and Speed metrics of the Decision tree model are as follows:
Precision of the model: 0.8532575291948371
Recall value: 0.7098445595854922
F1 Score of the model: 0.6837180286961946
Accuracy of the model: 0.6965363838576422
Time taken for predictions: 0.0364 seconds

