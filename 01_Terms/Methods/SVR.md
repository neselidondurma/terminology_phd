--- 
tags: [#linear_method]
created: 09-09-2025
--- 

# Support Vector Regression (SVR)
## 🔹 Definition / Formula
-  **Definition**: SVR is a regression method based on Support Vector Machines that aims to find a function $f(x)$ that deviates from the observed targets $y_i$ by at most $\epsilon$, while being as flat as possible. 
	**Optimization problem**:  
	  Minimize  
	  $$
	  \frac{1}{2} \| w \|^2
	  $$
	  subject to  
	  $$
	  \begin{cases}
	  y_i - (w \cdot x_i + b) \leq \epsilon + \xi_i \\
	  (w \cdot x_i + b) - y_i \leq \epsilon + \xi_i^*
	  \end{cases}
	  $$
	  with slack variables $\xi_i, \xi_i^* \geq 0$.

  
## 🔹 Explanation (in my words)
- SVR tries to fit data within a “tube” of width $2\epsilon$.  
- Errors within this tube are ignored; only points outside it matter.  
- Slack variables allow soft margins for non-perfect fits. 

## 🔹 Components
 - $w$: weight vector (defines the regression function)  
- $b$: bias term  
- $\epsilon$: margin of tolerance  
- $\xi_i, \xi_i^*$: slack variables for violations  
- $C$: regularization parameter (controls trade-off between flatness and tolerance)  

## 🔹 Context 
- Regression counterpart of Support Vector Classification (SVC).  
- Common in small/medium datasets where kernel methods are effective.  
- Useful for nonlinear regression with kernels (RBF, polynomial, etc.).  

## 🔹 Related
- [[Support_Vector_Machines]]  
- [[Kernel_trick]]  
- [[Regularization]]

## 🔹 Examples / Applications
- Predicting continuous variables like housing prices, bio-signal amplitudes, or financial forecasts. 

## 🔹 Source 
-  Vapnik, V. (1995). *The Nature of Statistical Learning Theory*.