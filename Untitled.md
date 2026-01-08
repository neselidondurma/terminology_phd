--- 
tags: [#speech
created: 11-12-2025
--- 
## 🔹 **Definition / Formula**

**MFCCs (Mel-Frequency Cepstral Coefficients)** are computed as:

$$\mathrm{MFCC}(t, k) = \mathrm{DCT}\left[\log \left( \mathbf{M}\, |X(t,f)|^2 \right)\right]_k$$

Where:

- $X(t,f)$ is the **Short-Time Fourier Transform (STFT)** of the signal.
    
- $|X(t,f)|^2$ is the **power spectrum**.
    
- $\mathbf{M}$ is the **Mel filterbank matrix**.
    
- $\log(\cdot)$ is element-wise logarithmic compression.
    
- $\mathrm{DCT}$ is the **Discrete Cosine Transform**.
    
- $k$ indexes the cepstral coefficient number (e.g., $k=0$ to $12$).
    

---

## 🔹 **Explanation (in my words)**

MFCCs are a **compact representation** of short slices of speech. They are designed to mimic the non-linear way the human ear perceives sound.

1. **Start from the Spectrogram:** The process begins with the power spectrum (from the STFT).
    
2. **Mimic Perception:** It is smoothed using the **Mel filterbank** to approximate human frequency perception (linear at low frequencies, logarithmic at high frequencies).
    
3. **Compress and Decorrelate:** The result is compressed with a logarithm and then decorrelated using a **Discrete Cosine Transform (DCT)**.
    

The final result is a **small vector** (e.g., 13 values per frame) that captures the broad spectral shape of speech (vocal tract characteristics) while discarding fine pitch and harmonic details.

> **Analogy:** Imagine taking a detailed color photo (spectrogram), blurring it (mel filters), reducing brightness variation (log), then summarizing it into a small set of numbers (DCT)—that’s MFCCs.


---

## 🔹 **Components**

| **Variable**   | **Description**                   | **Notes**                                                  |
| -------------- | --------------------------------- | ---------------------------------------------------------- |
| $x[n]$         | Time-domain audio signal          | Input                                                      |
| $X(t,f)$       | STFT matrix                       | Frequency content at time $t$                              |
| $              | X(t,f)                            | ^2$                                                        |
| $\mathbf{M}$   | Mel filterbank matrix             | Maps linear $\to$ Mel scale                                |
| $F_m$          | Number of Mel filterbank channels | E.g., 40, determines size of $\mathbf{M}$                  |
| $\log$         | Logarithmic function              | Compresses dynamic range (amplitude)                       |
| $\mathrm{DCT}$ | Discrete Cosine Transform         | Decorrelates mel channels to yield “cepstral” coefficients |
| $K$            | Number of MFCC coefficients kept  | E.g., 13, 20, or 40 (often $\le F_m$)                      |


---

## 🔹 **Context**

MFCCs are widely used in:

- **Speech processing**: ASR, speaker ID, classical speech emotion analysis
    
- **Digital biomarker research**: capturing vocal tract characteristics (common in depression/Parkinson’s studies)
    
- **Signal processing** textbooks and traditional audio pipelines
    
- **Classical ML models**: SVMs, HMMs, Gaussian mixture models
    

Before deep learning, MFCCs were the **dominant** speech feature; today log-mel spectrograms are more common for deep nets.

---

## 🔹 **Related**

- [[Mel Filterbank Energies]] — smoothing the STFT into perceptual bands
    
- [[Log-Mel Spectrogram]] — log-compressed mel energies
    
- [[STFT]] — short-time Fourier transform
    
- [[Cepstrum]] — “spectrum of a spectrum”; MFCCs are the mel-cepstrum
    
- [[Filterbank Features]] — general class including mel, gammatone, etc.
    
- [[DCT]] — transforms log-mel bands into decorrelated cepstral coefficients
    

---

### Worked Numerical Sketch (Simplified)

1. **Start:** Take a 25 ms speech frame $\to$ STFT yields 513 frequency bins.
    
2. Mel Filterbank: Multiply by a mel filterbank (e.g., 40 triangular filters) to get energies $E_m$:
    
    $$E_m = \mathbf{M}\, |X|^2 \quad (40 \text{ values})$$
    
3. Log Compression: Apply log compression:
    
    $$L_m = \log(E_m)$$
    
4. DCT to MFCCs: Apply DCT and typically keep only the lower $K=13$ coefficients:
    
    $$C_k = \mathrm{DCT}(L_m),\quad k=0\dots12$$
    
    Output: A 13-dimensional MFCC vector is used as the feature for that frame.
    

### Application Examples

- **Detecting Early Parkinson’s:** MFCCs often serve as baseline acoustic features capturing changes in vocal tract behavior due to the disease.
    
- **ASR/GMM-HMM Pipeline:** MFCCs + delta + delta-delta coefficients were the standard input for ASR systems for decades.
    

---

## 🔹 **Source**

- Rabiner & Schafer, _Digital Processing of Speech Signals_