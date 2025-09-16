--- 
tags: [#neuro]
created: 16-09-2025
--- 
## 🔹 Definition / Formula
- **Measurement Model**: y=υ+Λη+ǫ
- **Structural Model**: η=α+Bη+ζ

  
## 🔹 Explanation (in my words)
- **Structural Equation Modeling (SEM)** is a statistical framework for testing and estimating causal relationships among variables. It's especially useful for analyzing complex concepts that can't be directly measured, known as **latent variables**.
    
- Think of it like a detective building a case. The detective doesn't directly see "criminal intent" (η), but they can observe multiple pieces of evidence (y): a motive, a weapon, and a lack of alibi. SEM is the process of building a model that connects those pieces of evidence to the unobservable "criminal intent"

## 🔹 Components
-  y∈Ri: A vector of **observed items** (e.g., test scores).
    
- η∈Rp: A vector of **unobservable (latent) factors** (e.g., cognitive function).
    
- υ∈Ri: A vector of **intercepts** for the regression paths.
    
- Λ∈Ri×p: The **measurement slopes**, showing the relationship between observed and latent variables.
    
- ǫ∈Ri: The **residual error** for the observed items.
    
- α∈Rp: A vector of **intercepts** for the latent variables.
    
- B∈Rp×p: A non-singular matrix defining the **relationship between latent variables**.
    
- ζ∈Rp: The **residual error** for the latent variables.

## 🔹 Context 
- **Where it’s used:** SEM is a powerful tool used across various fields, including **neuroscience**, psychology, sociology, economics, and marketing.
    
- **When it appears:** It's used when researchers want to test a **hypothesized theoretical model** and analyze complex relationships involving latent variables, often in cross-sectional or longitudinal studies.

## 🔹 Related
- [[Confirmatory Factor Analysis]] - [[Path Analysis]]

## 🔹 Examples / Applications
**Case Study: Measuring Cognitive Decline in Alzheimer's Disease**

- **Latent Variables (η)**: "Executive Function" and "Memory." These can't be measured directly.
    
- **Observed Items (y)**: Scores on various neuropsychological tests, such as the Trail Making Test for executive function and the Rey Auditory Verbal Learning Test for memory.
    
- **Measurement Model**: SEM would show how well the scores from the Trail Making Test and other tests load onto the latent variable "Executive Function."
    
- **Structural Model**: The model could then test the hypothesis that a decline in "Executive Function" leads to a decline in "Memory" over time.
    
- This framework allows researchers to understand the relationships between the underlying cognitive processes and how they change as a person develops Alzheimer's disease, all while accounting for the inherent measurement error in the tests.

## 🔹 Source 
- Paper/book: tBA