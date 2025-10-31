--- 
tags: [#ml]
created: 31-10-2025
--- 
## 🔹Definition / Formula

$$
J(\theta) = \frac{1}{m} \sum_{i=1}^{m} L(y^{(i)}, \hat{y}^{(i)}) + \lambda R(\theta)
$$

where $J(\theta)$ is the objective function, $L$ is the loss function, $R(\theta)$ is the regularization term, and $\lambda$ is the regularization strength.

## 🔹 Explanation (in my words)

The objective function is the overall function that a machine learning model aims to optimize during training. It represents the "goal" or "target" that the learning algorithm tries to achieve by finding the optimal parameters $\theta$ that minimize (or maximize) this function.

## 🔹 Difference Between Objective Function, Cost Function, and Loss Function

- **Loss Function**: Measures the error for a **single training example** ($L(y^{(i)}, \hat{y}^{(i)})$)
- **Cost Function**: The **average loss** across the entire dataset ($\frac{1}{m} \sum_{i=1}^{m} L(y^{(i)}, \hat{y}^{(i)})$)
- **Objective Function**: The **overall function being optimized**, which may include the cost function plus additional terms like regularization ($J(\theta) = \text{Cost} + \lambda R(\theta)$)

In simple terms:
- **Loss** = error per example
- **Cost** = average loss across dataset  
- **Objective** = cost + regularization + any other constraints

## 🔹 Components

- $J(\theta)$ — objective function to be minimized
- $\theta$ — model parameters (weights and biases)
- $m$ — number of training examples
- $L(y^{(i)}, \hat{y}^{(i)})$ — loss for individual example $i$
- $R(\theta)$ — regularization term (e.g., L1, L2)
- $\lambda$ — regularization hyperparameter controlling trade-off

## 🔹 Context

Used as the primary optimization target in virtually all machine learning algorithms. During training, optimization algorithms (like gradient descent) iteratively update model parameters to minimize this function. The choice of objective function directly determines what kind of model we get.

## 🔹 Related

- [[Loss_Function]]
- [[Cost_Function]]
- [[Regularization]]
- [[Gradient_Descent]]
- [[Optimization_Algorithms]]
- [[Hyperparameter_Tuning]]

## 🔹 Common Types of Objective Functions

### 1. **Standard Objective**
$$
J(\theta) = \frac{1}{m} \sum_{i=1}^{m} L(y^{(i)}, \hat{y}^{(i)})
$$

### 2. **L2 Regularized Objective**
$$
J(\theta) = \frac{1}{m} \sum_{i=1}^{m} L(y^{(i)}, \hat{y}^{(i)}) + \frac{\lambda}{2m} \sum_{j=1}^{n} \theta_j^2
$$

### 3. **L1 Regularized Objective**
$$
J(\theta) = \frac{1}{m} \sum_{i=1}^{m} L(y^{(i)}, \hat{y}^{(i)}) + \frac{\lambda}{m} \sum_{j=1}^{n} |\theta_j|
$$

## 🔹 Examples / Applications

**Example 1: Linear Regression with L2 Regularization**
$$
J(\theta) = \frac{1}{2m} \sum_{i=1}^{m} (h_\theta(x^{(i)}) - y^{(i)})^2 + \frac{\lambda}{2m} \sum_{j=1}^{n} \theta_j^2
$$

**Example 2: Neural Network Classification**
$$
J(W,b) = -\frac{1}{m} \sum_{i=1}^{m} \sum_{k=1}^{K} y_k^{(i)} \log(\hat{y}_k^{(i)}) + \frac{\lambda}{2m} \sum_{l=1}^{L} \sum_{i=1}^{s_l} \sum_{j=1}^{s_{l+1}} (W_{ji}^{(l)})^2
$$

## 🔹 Optimization Perspective

The objective function provides:
- **Direction** for parameter updates via gradients
- **Stopping criterion** for training algorithms  
- **Model selection** criteria through its final value
- **Regularization** to prevent overfitting

## 🔹 Source

Bishop, C. M. (2006). Pattern Recognition and Machine Learning. Springer.

Boyd, S., & Vandenberghe, L. (2004). Convex Optimization. Cambridge University Press.