--- 
tags: [#ml]
created: 31-10-2025
--- 
## 🔹 Definition / Formula

- $$ \mathbf{h} = \text{Flatten}(\text{GAP}(\text{Conv}_L(\ldots \text{Conv}_1(\mathbf{X})))) $$
where

- $\text{Conv}_i$ are convolutional blocks (Conv → BatchNorm → ReLU → Pooling),
    
- $\text{GAP}$ denotes Global Average Pooling, and
    
- $\mathbf{h} \in \mathbb{R}^d$ is the final learned representation before classification.

---

## 🔹 Explanation (in my words)

- This vector is the **final feature representation** produced by the CNN before the fully connected classification head.
    
- Conceptually, it compresses spatial patterns into a compact summary describing _what_ features are present, independent of their exact location—similar to how the brain recognizes an object regardless of position or scale.
    

---

## 🔹 Components

- $\mathbf{X}$ – input image tensor (e.g., shape $[C, H, W]$).
    
- $\text{Conv}_i$ – convolutional layer with filters and nonlinearities.
    
- $\text{GAP}$ – Global Average Pooling that averages each feature map.
    
- $\mathbf{h}$ – flattened representation (embedding) vector used as input to the classifier.
    
- $L$ – total number of convolutional blocks.
    

---

## 🔹 Context

- Used in **Convolutional Neural Networks (CNNs)** for image, spatial omics, and signal data.
    
- Appears **just before the classifier layer**, serving as the learned latent representation capturing the network’s abstract understanding of the input.
    

---

## 🔹 Related

- [[Feature_Embedding]]
    
- [[Global_Average_Pooling]]
    
- [[Convolutional_Block]]
    
- [[Fully_Connected_Layer]]
    

---

## 🔹 Examples / Applications

- In **ResNet-50**, after the last convolutional block, a Global Average Pooling layer produces a $2048$-dimensional vector $\mathbf{h}$ for each image.  
    This vector is then passed to a dense layer with softmax for classification over $K$ categories.
    
    Example:
    
    $$ \mathbf{h} = \mathrm{GAP}(\text{Conv5\_x output}) \in \mathbb{R}^{2048}, \quad \hat{\mathbf{y}} = \mathrm{softmax}(\mathbf{W}\mathbf{h} + \mathbf{b}) $$
    

---

## 🔹 Source

- He, K. et al. (2016). _Deep Residual Learning for Image Recognition (ResNet)._ https://arxiv.org/abs/1512.03385