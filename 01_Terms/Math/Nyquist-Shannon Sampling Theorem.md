--- 
tags: [, #math]
created: 18-09-2025
--- 
## 🔹 Definition / Formula
- : **Nyquist-Shannon Sampling Theorem**: fmax​=fs​/2

  
## 🔹 Explanation (in my words)
-The **sampling rate** (fs​) of an audio file is the number of times the sound wave is measured per second. While a higher sampling rate allows for a wider range of frequencies, the actual sound content in the file might only occupy a smaller portion of that range. For example, a speech signal sampled at 48 kHz (with a theoretical maximum frequency of 24 kHz) may not contain any meaningful frequencies above 16 kHz. This is because human speech itself has a limited **bandwidth**; most of the information is concentrated in the lower frequencies.

## 🔹 Components
- **fs​**: Sampling rate (in Hz), the number of samples taken per second.
    
- **fmax​**: The maximum frequency that can be accurately captured by a given sampling rate.

## 🔹 Context 
- This concept is fundamental to **digital audio signal processing** and is crucial for fields like **speech technology**, **music production**, and **telecommunications**.
    
- It appears whenever you are dealing with the digitization of any continuous signal, but it is especially relevant when discussing audio quality and efficiency. Understanding effective bandwidth is important for a model to be efficient, as processing unnecessary data can be computationally expensive.

## 🔹 Related
- [[Aliasing]] - [[Bandwidth]] 

## 🔹 Examples / Applications
- A speech file is recorded at a sampling rate of 48 kHz. Although this allows frequencies up to 24 kHz, a spectral analysis of the file shows that the signal's energy (and thus its useful content) drops off significantly above 16 kHz. This tells us the file's **effective bandwidth** is closer to 16 kHz, not the theoretical 24 kHz. For a **speech-to-text model**, using this 48 kHz file might not offer a performance benefit over using a 32 kHz file (with a maximum frequency of 16 kHz) if the higher frequencies are just empty space.

## 🔹 Source 
