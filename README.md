# Principal Component Analysis (PCA) Explained

## Introduction

Suppose you have **2 features**:  

- `x1` = height  
- `x2` = weight  

If you plot them, you’ll notice that the cloud of points is **elongated along a diagonal**.  

That diagonal represents the **direction of maximum variance**—the axis along which the data spreads the most.  

PCA asks:  
👉 “Which directions capture most of the spread (variance) of the data?”

### Example Figure

![PCA Example](figures/pca_example.png)  
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

## References

- [PCA on Wikipedia](https://en.wikipedia.org/wiki/Principal_component_analysis)  
- [A Friendly Introduction to PCA](https://towardsdatascience.com/principal-component-analysis-for-dummies-8c7f5a7f3d18)
