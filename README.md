Here's a structured README based on the provided project description and Jupyter Notebook:

* * *

Quantum-Chemical Insights Using Machine Learning
================================================

Overview
--------

This project leverages machine learning techniques to uncover relationships between molecular geometry and electronic properties, specifically focusing on **atomization energy**. Using the **QM7 dataset**, we apply **ridge regression models** and **explainable AI techniques** to predict atomization energies and identify the molecular substructures contributing to these predictions.

By understanding how atomic arrangements affect atomization energy, this work can assist in designing new molecules, potentially aiding drug discovery or material development.

Dataset
-------

**QM7 Dataset**:

*   **Source**: [Quantum Machine](http://quantum-machine.org/data/qm7.mat)
*   **Contents**:
    *   **7165 organic molecules** with up to 23 atoms each.
    *   **R**: 3D coordinates of atoms (shape: 7165×23×3).
    *   **Z**: Atomic numbers corresponding to atoms in each molecule.
        *   1: Hydrogen (H)
        *   6: Carbon (C)
        *   7: Nitrogen (N)
        *   8: Oxygen (O)
        *   16: Sulfur (S)
    *   **T**: Atomization energies (target values).

Project Structure
-----------------

1.  **Data Representation**  
    Molecules are decomposed into:
    
    *   **Individual atoms**: Represented using one-hot encoding of atom types.
    *   **Pairs of atoms**: Encoded based on atom types and distances between atoms.
2.  **Machine Learning Model**  
    A **ridge regression model** is used to predict atomization energies:
    
    *   The model takes summed atom/pair representations as input features.
    *   Regularization is applied to control overfitting.
3.  **Explainability**
    
    *   Contribution of each atom or atom pair to the predicted energy is quantified.
    *   This helps identify specific molecular structures that influence atomization energy.
4.  **Experiments**
    
    *   **Atom-Based Representation**:
        *   Molecules are represented by the sum of their atoms' one-hot vectors.
        *   Achieves a mean absolute error of ~15 kcal/mol.
    *   **Pair-Based Representation**:
        *   Incorporates pairwise distances and atom types.
        *   Achieves improved prediction accuracy with an error of ~6 kcal/mol.

Setup Instructions
------------------

1.  **Clone the repository:**
    
    ```bash
    git clone <repository_url>
    cd <repository_folder>
    ```
    
2.  **Install dependencies:**
    
    ```bash
    pip install -r requirements.txt
    ```
    
3.  **Download the QM7 dataset:**
    
    *   Download from [here](http://quantum-machine.org/data/qm7.mat) and place it in the project directory.
4.  **Run the notebook:**
    
    ```bash
    jupyter notebook projectTwo.ipynb
    ```
    

Key Results
-----------

*   Ridge regression with simple atom-based features provides reasonable predictions of atomization energy.
*   Including pairwise distances significantly improves the model's accuracy.
*   Explainable AI techniques help visualize which atoms or bonds influence the molecule's stability.

Visualizations
--------------

*   **Molecular Structures**: 3D scatter plots of atoms with bond connections based on distances.
*   **Feature Contributions**: Visual breakdowns of how individual atoms or pairs contribute to predicted energies.
*   **Pairwise Potentials**: Plots showing how distance between atom pairs influences energy.

Future Work
-----------

*   Explore more complex ML models (e.g., neural networks) to improve predictive accuracy.
*   Extend the dataset to larger or more complex molecules.
*   Apply techniques to other electronic properties beyond atomization energy.

References
----------

*   [QM7 Dataset](http://quantum-machine.org/data/qm7.mat)
*   Montavon, G. (2024). _Lab Machine Learning for Data Science, Freie Universität Berlin._

* * *

Let me know if you need any specific sections modified!