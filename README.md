# Data Management Assignment

This is my assignment for STQD6324 Data Management. I use PySpark MLlib to classify the Iris dataset. Three models are compared: Decision Tree, Multilayer Perceptron (MLP), and Logistic Regression.

## Dataset

The Iris dataset has 150 samples of iris flowers from three species: setosa, versicolor, and virginica. Each sample has four features: sepal length, sepal width, petal length, and petal width. The goal is to predict the species from these four numbers.

## What I Did

1. Load data : I downloaded the dataset and loaded it into a Spark DataFrame.  
2. Prepare data : I changed the species names into numbers (0,1,2) and combined the four feature columns into one feature vector.  
3. Split data :I split the dataset into training (128 samples) and test (22 samples) sets.  
4. Train models : I trained three models using Spark MLlib:
   - Decision Tree
   - Multilayer Perceptron (MLP)
   - Logistic Regression
5. Tuning : For Decision Tree and Logistic Regression, I used grid search and 3‑fold cross‑validation to pick the best hyperparameters. For MLP I used a simple structure [4,2,3] without tuning.
6. Evaluate : I measured accuracy, F1 score, and precision. I also looked at confusion matrices to see where each model makes mistakes.
7. Compare : I compared the three models and picked the best one.

## Results

Here are the scores on the test set:

<img width="330" height="145" alt="image" src="https://github.com/user-attachments/assets/b6661ef3-a1c2-41c6-b80c-7398aadfe62c" />


And i also calculate confusion matrix :
- All models can classify setosa perfectly.
- Versicolor and virginica are sometimes mixed up. DT and LR each made 2 mistakes but in opposite directions. MLP had no mistakes on this small test set.

Best model: MLP got perfect scores on this test run. But the test set is very small (only 22 samples), and I didn't tune the MLP. So Decision Tree is the safer and more explainable choice if I had to pick one for a real project.

## Files in This proj

- code.ipynb – Jupyter notebook with all the code and explanations.
- iris.data – The Iris dataset file.
- README.md

## How to Run

1. Access google colab, import this notebook.
2. Download the iris dataset .
3. Open the notebook and run all cells.
