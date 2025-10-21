# Multi-Classification Using KD-Tree and Linear Classifiers

---

## 1. Overview

In this project, I implemented two classification techniques: **Linear Classification** and **Nearest Neighbor Classification (via KD-Tree)**, using data generated from **Gaussian distributions**.  

The project is structured around **five tasks**, each demonstrating a different aspect of data classification.

---

## 2. Tasks

### Task 1: KD-Tree

A custom **KD-Tree data structure** was designed and implemented in Python to handle 2D data and perform **1-nearest-neighbor searches**.  
The tree recursively splits data by the **median of the current axis** (alternating between x and y) to build a balanced structure. 

- **Implementation:** Custom KD-Tree with recursive splitting  
- **Functionality:** Supports 1-nearest-neighbor search for a given query point  
- **Usage:** Used later for classification based on nearest neighbors  

---

### Task 2: Constructing a Simple Dataset

In this task, **5,000 data points** were drawn from two distinct but overlapping **2D multivariate Gaussian distributions**, creating a dataset of **10,000 points** in total.  
The dataset was then split into **training** and **test** sets.

- **Data Generation:** Generated data using 2D Gaussian distributions with distinct means and covariances  
- **Partitioning:** Randomly split into training and test sets  
- **Resulting Data:**  
  - `X` of shape (10000, 2)  
  - `y` of size 10,000 (0 for first distribution, 1 for second)

---

### Task 3: Linear Classifier

Using the training data from Task 2, a **maximum-likelihood linear least squares** classifier was constructed using the equation:

$$
\beta = (X^T X)^{-1} X^T y
$$

- **Classification:** Points were classified based on whether  
$ x^T \beta > 0.5 $ (Class 1) or $ \le 0.5 $ (Class 0).
- **Accuracy Calculation:** Computed by comparing true and predicted labels on the test set  
- **Visualization:** Plots included:
  - Training set points for Class 0 and Class 1  
  - Correctly and incorrectly classified test points for both classes  

---

### Task 4: Nearest Neighbor Classification

The same training and test data from Task 2 was used, but this time the classification was done using a **KD-Tree-based nearest neighbor** search.

- **KD-Tree:** Training data organized into a KD-Tree  
- **Classification:** For each test point, the nearest training neighbor was found, and its class label was assigned  
- **Accuracy Calculation:** Compared with the linear classifier’s performance  
- **Visualization:** Plots showing correctly and incorrectly classified test points  

---

### Task 5: Increasing Complexity

A new dataset was generated for this task, consisting of **10,000 points** drawn from **ten different overlapping Gaussian distributions**.  
Five of the distributions were assigned to **Class 0** and five to **Class 1**, making the classification problem more complex.

- **Data Generation:** Generated 1,000 samples each from ten overlapping Gaussian distributions  
- **Classification:** Applied both linear and KD-Tree-based nearest neighbor classifiers  
- **Accuracy:** Computed and compared between both methods  
- **Visualization:** Plots showing classification results for both methods, highlighting correct and incorrect points  

---

## 3. Instructions to Run

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd <repository-folder>

2. **Run the Python script**
   - Ensure you have the required libraries installed:
     ```bash
     pip install numpy matplotlib
     ```
   - Execute the script to generate the results:
     ```bash
     python main.py
     ```

3. **View the visualizations**
   - Several plots will be generated, showing data distributions, training/test splits, and classification results.

---

## 4. Requirements

- Python 3.x  
- numpy  
- matplotlib  

---

## 5. Results

- **Task 1:** Successfully implemented a KD-Tree that supports efficient 1-nearest-neighbor search  
- **Task 2:** Generated data from two overlapping Gaussian distributions, split into training and test sets  
- **Task 3:** Achieved high accuracy using a linear classifier on the simple dataset  
- **Task 4:** Implemented nearest neighbor classification using the KD-Tree, with comparable accuracy to the linear classifier  
- **Task 5:** Successfully classified more complex data generated from multiple overlapping Gaussian distributions using both classifiers  

---

## 6. Future Improvements

- **Multi-dimensional KD-Tree:** Expand the KD-Tree to support higher-dimensional data  
- **Different Classifiers:** Implement classifiers like **Support Vector Machines (SVM)** and **Random Forest** to compare performance on complex datasets  
- **Hyperparameter Tuning:** Explore **cross-validation** techniques to improve model performance, especially on more complex data  


