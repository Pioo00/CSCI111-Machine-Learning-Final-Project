Pokemon Machine Learning Project

------------------------------------------------------------

Description

This is our classification and clustering project on Pokemon stats, done for CSCI 111 Machine Learning.

We're using the Pokemon with stats dataset from Kaggle, which has 800 Pokemon and 7 numeric battle stats, to answer two questions.

The first is whether we can predict if a Pokemon is Legendary. We trained KNN and a Decision Tree, each on three versions of the data (raw, Min-Max scaled, and Standard scaled), so six models in total.

The second is whether Pokemon naturally group together based on their stats in a way that lines up with the Legendary label, using K-Means clustering. The clustering never sees the label itself, so it's a good way to check if Legendaries are just naturally different.

We also wanted to see how much normalization actually matters, so we compared the raw data against Min-Max scaling and Standard scaling side by side.

Kaggle dataset: https://www.kaggle.com/datasets/abcsds/pokemon

------------------------------------------------------------

Repository Structure

Pokemon.csv
The raw dataset we started with.

cleaning01.ipynb
First notebook. Loads the raw data, drops duplicate and Mega entries, and splits everything into features (X) and label (y).

datasets_scaling02.ipynb
Second notebook. Takes the cleaned features and builds the three versions we compare throughout the project: D1 (raw), D2 (Min-Max scaled), D3 (Standard scaled).

classification03.ipynb
Third notebook. Trains KNN and Decision Tree on D1, D2, and D3, then reports accuracy, precision, recall, and confusion matrices for all six models, and picks the best one.

clustering04.ipynb
Fourth notebook. Runs K-Means on D1, D2, and D3, checks Inertia and Silhouette Score across K = 2 to 10, picks the best K, and plots the final clusters.

cleaned_pokemon.csv
Deduplicated dataset, saved out by cleaning01.

X_clean.csv and y_clean.csv
Features and label, also saved out by cleaning01.

D1.csv, D2.csv, D3.csv
The three scaled datasets, saved out by datasets_scaling02.

confusion_matrices_phase3.png
Confusion matrix grid for all six classification models.

decision_tree_full.png
A full visualization of the best-performing Decision Tree.

elbow_silhouette.png
Elbow Method and Silhouette Score plots used to pick the best K.

clustering_scatter.png
The final scatter plot comparing our clusters to the true Legendary labels.

------------------------------------------------------------

Requirements

You'll need Python 3.9 or later, plus these packages: pandas, numpy, scikit-learn, matplotlib, seaborn.

Install everything with:

pip install pandas numpy scikit-learn matplotlib seaborn

------------------------------------------------------------

Quick Start / Run Order

Open the notebooks in Jupyter Notebook, JupyterLab, or VS Code, and run each one top to bottom.

The four notebooks have to be run in this exact order, since each one depends on files saved by the one before it.

1. cleaning01.ipynb
Reads Pokemon.csv, saves cleaned_pokemon.csv, X_clean.csv, and y_clean.csv.

2. datasets_scaling02.ipynb
Reads X_clean.csv and y_clean.csv, saves D1.csv, D2.csv, and D3.csv.

3. classification03.ipynb
Reads D1.csv, D2.csv, D3.csv, and y_clean.csv, saves confusion_matrices_phase3.png and decision_tree_full.png.

4. clustering04.ipynb
Reads D1.csv, D2.csv, D3.csv, and y_clean.csv, saves elbow_silhouette.png and clustering_scatter.png.

That said, all the intermediate csv and png files are already sitting in this repo, so the notebooks will still run fine even out of order or one at a time. Each one just picks up the input files it needs from the directory.

------------------------------------------------------------

Credits

Add team member names and student numbers here.

------------------------------------------------------------

Note on documentation structure

This README's structure and section breakdown (Description, Repository Structure, Quick Start) follows the guidelines outlined in Casmir Onyekani, "How to Structure Your README File - README Template Example", freeCodeCamp, 2025.
Source: https://www.freecodecamp.org/news/how-to-structure-your-readme-file/
