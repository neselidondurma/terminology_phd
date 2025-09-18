--- 
tags: [#term, #formula, #ml, #neuro, #math]
created: 18-09-2025
--- 
## 🔹 Definition / Formula
- : Speech enhancement is a signal processing technique that aims to improve the quality and intelligibility of a speech signal. This is typically done by reducing or removing unwanted noise, reverberation, and other distortions from an audio recording while preserving the original speech content.
- x(t)=s(t)+n(t), where x(t) is the observed noisy speech signal, s(t) is the clean speech signal, and n(t) is the unwanted noise. The goal of speech enhancement is to estimate the clean speech signal, s^(t), from the noisy observation x(t), such that s^(t)≈s(t).

  
## 🔹 Explanation (in my words)
-  Speech enhancement is like a digital ear cleaner. It takes a noisy audio recording, such as a phone call in a crowded coffee shop, and tries to scrub out all the background sounds, leaving behind only the clear voice of the person speaking.
    
- Imagine you're trying to have a conversation with a friend at a loud party. Your brain automatically filters out the music and other people's chatter to focus on what your friend is saying. Speech enhancement is the computational equivalent of that mental process, but for audio signals.
## 🔹 Components
- **Noise Model**: A representation of the characteristics of the unwanted noise, which can be stationary (e.g., a fan humming) or non-stationary (e.g., a car passing by).
    
- **Speech Model**: A representation of the characteristics of the speech signal itself.
    
- **Algorithm/Filter**: The core method used to separate the speech from the noise. This could be a traditional signal processing algorithm like a **Wiener filter** or a modern **deep neural network (DNN)**.
    
- **Evaluation Metrics**: Measures to assess the quality of the enhanced speech, such as **Signal-to-Noise Ratio (SNR)**, Perceptual Evaluation of Speech Quality (PESQ), or Short-Time Objective Intelligibility (STOI).

## 🔹 Context 
- **Where it’s used**: Widely used in **audio signal processing**, **machine learning**, and **telecommunications**.
    
- **When it appears**: It serves as a crucial pre-processing step for many speech-related applications, particularly in noisy or challenging acoustic environments. It's often a front-end for **Automatic Speech Recognition (ASR)** and **speaker recognition** systems to improve their accuracy.

## 🔹 Related
- [[Automatic Speech Recognition (ASR)]] - [[Signal Processing]] - [[Noise Reduction]] - [[Wiener Filter]]

## 🔹 Examples / Applications
-  **Mobile Phones and VoIP**: Improves call quality by suppressing background noise and echo.
    
- **Hearing Aids**: Makes it easier for users to understand speech in noisy situations.
    
- **Virtual Assistants**: Ensures that voice commands are understood accurately, even in loud rooms.
    
- **Audio/Video Conferencing**: Enhances the clarity of participants' voices during meetings.

## 🔹 Source 
- Paper/book: [Zotero link]