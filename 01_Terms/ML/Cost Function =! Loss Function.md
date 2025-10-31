--- 
tags: [#ml]
created: 31-10-2025
--- 
## 🔹 Definition / Formula

$$
L(y, \hat{y}) = -\sum_{i=1}^{K} y_i \log(\hat{y}_i)
$$

where $L$ is the cost (loss) function—most commonly, the categorical cross-entropy used for CNN classification tasks.

## 🔹 Explanation (in my words)

The cost function measures how far the model's predictions are from the true labels.

Intuitively, it acts like a "discomfort signal": the larger the error between predicted and actual outputs, the higher the loss, guiding the network to adjust its weights during training to minimize this quantity.

## 🔹 Difference Between Cost Function and Loss Function

- **Loss Function**: Calculates the error for a **single training example**. It measures how well the model performs on one specific data point.

- **Cost Function**: Computes the **average loss** across the **entire training dataset** (or a batch). It's the overall objective that the model tries to minimize during training.

In practice:
- **Loss** = error for one example
- **Cost** = average loss over all examples --> can also include the regularisation 

For categorical cross-entropy:
- **Loss**: $L(y^{(i)}, \hat{y}^{(i)}) = -\sum_{j=1}^{K} y_j^{(i)} \log(\hat{y}_j^{(i)})$ (for example $i$)
- **Cost**: $J = \frac{1}{m} \sum_{i=1}^{m} L(y^{(i)}, \hat{y}^{(i)})$ (average over $m$ examples)

## 🔹 Components

- $y$ — true label (one-hot encoded vector)
- $\hat{y}$ — predicted probability distribution after softmax
- $K$ — number of classes
- $L$ — loss (scalar) minimized via gradient descent

## 🔹 Context

Used in supervised CNN training for tasks such as image or patch classification.

Computed after the forward pass and before backpropagation; it quantifies prediction error and drives weight updates.

## 🔹 Related

- [[Cross_Entropy_Loss]]
- [[Binary_Cross_Entropy]] 
- [[Mean_Squared_Error]]
- [[Gradient_Descent]]
- [[Backpropagation]]

## 🔹 Examples / Applications

**Example:**
For a 3-class problem with $y = [0, 1, 0]$ (true class = 2) and $\hat{y} = [0.2, 0.7, 0.1]$, the loss is:

$$
L = -(1) \cdot \log(0.7) \approx 0.357
$$

A smaller $L$ indicates better prediction alignment.

## 🔹 Source

Goodfellow, I., Bengio, Y., & Courville, A. (2016). Deep Learning. MIT Press.
https://www.deeplearningbook.org/