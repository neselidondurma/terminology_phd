--- 
tags: [#ml]
created: 31-10-2025
--- 
## 🔹 Definition / Formula

**General Update Rule:**
$$
\theta_{t+1} = \theta_t - \eta \cdot g_t
$$

where:
- $\theta_t$: parameters at time step $t$
- $\eta$: learning rate
- $g_t$: update direction (varies by optimizer)

## 🔹 Explanation (in my words)

Optimizers are algorithms that adjust model parameters to minimize the objective function. They determine *how* to update weights and biases based on the gradients computed during backpropagation. Think of them as "navigation systems" that guide the model through the complex landscape of the objective function to find the optimal parameters.

## 🔹 Relationship with Loss, Cost, and Objective Functions

- **Loss Function**: Provides error signal per example → gradients
- **Cost Function**: Average loss across dataset → overall gradient direction  → OPTIMISER TRIES TO MINIMISE THE COST FUNCTION
- **Objective Function**: Cost + regularization → what we actually optimize
- **Optimizer**: Determines *how* to update parameters based on gradients from objective function

**The Optimization Process:**
1. Compute loss for each example
2. Aggregate to cost function
3. Add regularization to form objective function
4. Compute gradients $\nabla_\theta J(\theta)$
5. Optimizer updates parameters: $\theta \leftarrow \theta - \eta \cdot \text{update\_rule}(\nabla_\theta J(\theta))$

## 🔹 Components

### Core Components:
- **Parameters ($\theta$)**: Weights and biases being optimized
- **Learning Rate ($\eta$)**: Step size for parameter updates
- **Gradients ($\nabla_\theta J$)**: Derivatives of objective function w.r.t. parameters
- **Update Rule**: Algorithm-specific computation of update direction

### Advanced Components:
- **Momentum**: Accumulated past gradients for smoother updates
- **Adaptive Learning Rates**: Per-parameter learning rate adjustments
- **Bias Correction**: Corrections for initialization bias in adaptive methods

## 🔹 Context

Used in the training loop of all deep learning models after forward pass and loss computation. The choice of optimizer significantly impacts:
- Training speed and convergence
- Final model performance
- Stability during training
- Ability to escape local minima

## 🔹 Common Optimizers

### 1. **Stochastic Gradient Descent (SGD)**
$$
\theta_{t+1} = \theta_t - \eta \nabla_\theta J(\theta_t)
$$

### 2. **SGD with Momentum**
$$
\begin{aligned}
v_t &= \beta v_{t-1} + (1 - \beta) \nabla_\theta J(\theta_t) \\
\theta_{t+1} &= \theta_t - \eta v_t
\end{aligned}
$$

### 3. **Adam (Adaptive Moment Estimation)**
$$
\begin{aligned}
m_t &= \beta_1 m_{t-1} + (1 - \beta_1) \nabla_\theta J(\theta_t) \\
v_t &= \beta_2 v_{t-1} + (1 - \beta_2) (\nabla_\theta J(\theta_t))^2 \\
\hat{m}_t &= \frac{m_t}{1 - \beta_1^t} \\
\hat{v}_t &= \frac{v_t}{1 - \beta_2^t} \\
\theta_{t+1} &= \theta_t - \eta \frac{\hat{m}_t}{\sqrt{\hat{v}_t} + \epsilon}
\end{aligned}
$$

### 4. **RMSProp**
$$
\begin{aligned}
v_t &= \beta v_{t-1} + (1 - \beta) (\nabla_\theta J(\theta_t))^2 \\
\theta_{t+1} &= \theta_t - \eta \frac{\nabla_\theta J(\theta_t)}{\sqrt{v_t} + \epsilon}
\end{aligned}
$$

## 🔹 Related

- [[Gradient_Descent]]
- [[Backpropagation]]
- [[Learning_Rate_Scheduling]]
- [[Loss_Function]]
- [[Cost_Function]]
- [[Objective_Function]]
- [[Hyperparameter_Tuning]]

## 🔹 Optimization Landscape Analogy

| Concept | Real-world Analogy |
|---------|-------------------|
| **Objective Function** | Mountain landscape to navigate |
| **Parameters** | Your current position |
| **Gradients** | Slope/direction of steepest descent |
| **Learning Rate** | Step size |
| **Optimizer** | Navigation strategy (zigzag, momentum, etc.) |
| **Local Minima** | Valleys in the landscape |

## 🔹 Examples / Applications

**Example: Training a CNN with Adam Optimizer**
```python
# Pseudo-code example
for epoch in range(epochs):
    for batch in dataloader:
        # Forward pass: compute loss (per example)
        predictions = model(batch.images)
        loss = cross_entropy_loss(predictions, batch.labels)
        
        # Backward pass: compute gradients of objective function
        optimizer.zero_grad()
        loss.backward()  # Computes ∇J(θ)
        
        # Optimizer update: adjusts parameters
        optimizer.step()  # Applies Adam update rule