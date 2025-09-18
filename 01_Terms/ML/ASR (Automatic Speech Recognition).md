--- 
tags: [#ml]
created: 18-09-2025
--- 
## 🔹 Definition / Formula
- : P(W∣O) is the probability of a word sequence
	- **W** given an acoustic observation sequence
	- **O**. This is often modeled using the
		- **Bayes' theorem**: P(W∣O)=P(O)P(O∣W)P(W)​, 
			- where P(O∣W) is the **acoustic model**, 
			- P(W) is the **language model**, 
			- P(O) is the evidence.

  
## 🔹 Explanation (in my words)
-  Automatic Speech Recognition is a technology that converts spoken words into text. It's essentially the process of a computer listening to a person speak and transcribing what they said.
    
- Think of it as a super-smart translator for sound. Instead of translating one language to another, it translates the sounds of human speech into written words

## 🔹 Components
- **Acoustic Model**: Maps sound (phonemes, acoustic features) to speech units (e.g., words).
    
- **Language Model**: Predicts the likelihood of a sequence of words appearing together in a specific language. This helps resolve ambiguities, like distinguishing "recognize speech" from "wreck a nice beach."
    
- **Pronunciation Dictionary**: A lexicon that maps words to their phonetic pronunciations.
    
- **Decoder**: Combines the acoustic and language models to find the most probable sequence of words for a given audio input.

## 🔹 Context 
-  **Where it’s used**: Primarily in **machine learning** and **natural language processing (NLP)**. It's a foundational technology for voice-controlled devices and applications.
    
- **When it appears**: It's a core component of many modern systems, especially those involving human-computer interaction via voice, like virtual assistants and transcription services.

## 🔹 Related
-[[Natural Language Processing]] - [[Voice Recognition]] - [[Acoustic Model]] - [[Language Model]]

## 🔹 Examples / Applications
-  **Virtual Assistants**: When you say "Hey Siri" or "Hey Google," ASR is what converts your voice command into text that the device can process.
    
- **Transcription Services**: Services like Otter.ai or YouTube's automatic captions use ASR to convert audio and video content into written transcripts.
    
- **Hands-Free Operation**: It enables navigation systems in cars or smart home devices to be controlled by voice, improving safety and convenience.

## 🔹 Source 
- Paper/book: