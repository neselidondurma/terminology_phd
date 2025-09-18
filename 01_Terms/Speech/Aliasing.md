--- 
tags: [#speech]
created: 18-09-2025
--- 
## 🔹 Definition / Formula
- : The distortion of a signal caused by an insufficient sampling rate, where frequencies above the Nyquist frequency "fold back" into the audible spectrum.

  
## 🔹 Explanation (in my words)
- is an unwelcome side effect of digitization. When converting a continuous analog signal to a discrete digital one, if you don't take enough samples per second (i.e., the sampling rate is too low), high-frequency components that cannot be represented in the digital signal get misinterpreted and appear as new, lower frequencies. This creates unwanted distortion or noise.

## 🔹 Components
-  **fs​**: Sampling rate (in Hz), the number of samples taken per second.
    
- **fNyquist​**: The Nyquist frequency, which is half the sampling rate (fs​/2). This is the theoretical maximum frequency that can be captured without aliasing.
    

## 🔹 Context 
- This phenomenon is a fundamental concern in **digital signal processing** and is a critical consideration in **audio engineering**, **telecommunications**, and **speech technology**.
    
- To prevent aliasing, an **anti-aliasing filter** is used to remove all frequencies above the Nyquist frequency _before_ the signal is digitized.

## 🔹 Related
**[[Nyquist-Shannon Sampling Theorem]]** - [[Sampling Rate]] - **[[Anti-aliasing Filter]]**

## 🔹 Examples / Applications
- A classic visual example of aliasing is when a spoked wheel in a movie appears to be spinning backward. The camera's frame rate (the sampling rate) is too slow to capture the true motion, leading to a distorted representation.
    
- In a telephone call, human speech can have frequencies up to around 8 kHz, but the system only samples at 8 kHz. This sets the Nyquist frequency to 4 kHz. The system uses a low-pass filter to cut off all frequencies above 4 kHz to prevent aliasing, which is why phone calls sound different from high-fidelity recordings.

## 🔹 Source 
