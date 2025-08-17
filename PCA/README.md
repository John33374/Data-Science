# Principal Component Analysis (PCA) Explained

## Introduction

Suppose you have **2 features**:  

- `x1` = height  
- `x2` = weight  

If you plot them, you’ll notice that the cloud of points is **elongated along a diagonal**.  

That diagonal represents the **direction of maximum variance**—the axis along which the data spreads the most.  

PCA asks:  
👉 “Which directions capture most of the spread (variance) of the data?”

*The diagonal direction represents the principal component—the direction of maximum variance.*

---

## What is PCA?

Principal Component Analysis is a **dimensionality reduction technique** that:  

1. Finds the directions (principal components) where data varies the most.  
2. Projects the data onto these directions.  
3. Reduces the number of features while retaining most of the variance.  

### Why Use PCA?

- Simplifies complex datasets.  
- Helps visualize high-dimensional data.  
- Reduces computational cost for machine learning algorithms.  

---

## How PCA Works (Step by Step)

1. **Standardize the data** (mean = 0, variance = 1).  
2. **Compute the covariance matrix** to understand how features vary together.  
3. **Compute eigenvectors and eigenvalues** of the covariance matrix.  
   - Eigenvectors = directions of maximum variance.  
   - Eigenvalues = magnitude of variance along each direction.  
4. **Sort eigenvectors by eigenvalues** in descending order.  
5. **Project the data** onto the top `k` eigenvectors to reduce dimensions.

---

## Example
# Principal Component Analysis (PCA) - Geometric Intuition

## 1. Variance = Spread of Data

Suppose you have 2 features: 
- $x_1$ = height
- $x_2$ = weight

If you plot them, you'll see that the cloud of points is elongated along some diagonal.

**That diagonal is the direction of maximum variance** → where data spread is largest.

So PCA asks:
👉 *"Which directions capture most of the spread (variance) of the data?"*

---

## 2. Covariance Matrix = Captures Relationships

For 2D case:

$$
C = \begin{bmatrix}
Var(x_1) & Cov(x_1,x_2) \\
Cov(x_1,x_2) & Var(x_2)
\end{bmatrix}
$$

- **Large covariance** means the two features vary together (strong diagonal trend)
- **Zero covariance** means they're uncorrelated

---

## 3. Eigenvectors = Directions of Variance

We solve:

$$
Cv = \lambda v
$$

Where:
- $v$ = direction (axis in feature space)
- $\lambda$ = variance along that direction

Key insights:
👉 The eigenvector with the largest eigenvalue points to the direction where the data has the greatest spread  
👉 The second eigenvector (perpendicular) points to the next strongest spread  

---

## 4. Geometric Picture

Imagine rotating the coordinate system:
- **Original axes**: $(x_1, x_2)$  
- **New axes**: eigenvectors of $C$  

Now the data variance is aligned with the axes:
- Along the first axis = maximum variance  
- Along the second = smaller variance  

This rotation decorrelates the data → covariance in new basis is diagonal ($\Lambda$).

---

## 5. Example (Visual)

Suppose a set of data X:

$$
X = \begin{bmatrix}
X1.1 & X1.2 \\
X2.1 & X2.2
\end{bmatrix}
$$


Suppose data is elongated along line $y = x$.

Covariance matrix might look like:

$$
C = \begin{bmatrix}
2 & 2 \\
1 & 3
\end{bmatrix}
$$

Eigenvectors ≈ $[1,1]$ (diagonal) and $[1,-1]$ (anti-diagonal)  

Eigenvalues:  
- $\lambda_1$ big (~5.9)  
- $\lambda_2$ small (~0.1)  

**Interpretation**:  
Most variance is along $[1,1]$ → the diagonal direction.  
Almost no variance along $[1,-1]$.  

So PCA says: project onto $[1,1]$ → reduce from 2D to 1D while keeping almost all variance.

---

## 6. Summary (Geometric Intuition)


![PCA Example](/images/Pca.png)  
*The diagonal direction represents the principal component—the direction of maximum variance.*

1. Covariance matrix tells us how data is spread  
2. Eigenvectors = directions of variance  
3. Eigenvalues = how much variance along each direction  
4. PCA = rotate axes to align with these directions, then keep only the top ones for dimension reduction  

## References

- [PCA on Wikipedia](https://en.wikipedia.org/wiki/Principal_component_analysis)  
- [A Friendly Introduction to PCA](https://towardsdatascience.com/principal-component-analysis-for-dummies-8c7f5a7f3d18)

