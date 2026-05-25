# 🛡 GemmaShield

## AI for Social Good — Multimodal AI Voice Scam Detection System

GemmaShield is a lightweight multimodal AI system designed to combat the growing threat of AI-generated voice scams, telecom fraud, and voice cloning attacks.

Built for the Gemma 4 Developer Competition (Track D: AI for Social Good), the project combines acoustic spoof detection, speech recognition, and LLM-based reasoning to provide real-time explainable scam risk analysis.

---

# 🌍 Why This Matters

AI voice cloning technologies are becoming increasingly accessible and dangerous.

Fraudsters can now:

* impersonate family members
* imitate public figures
* conduct telecom scams
* manipulate victims emotionally
* bypass traditional security checks

GemmaShield aims to provide an accessible and deployable AI defense system that helps users identify suspicious synthetic voices before harm occurs.

This project focuses on:

* public safety
* anti-fraud protection
* AI transparency
* accessible AI security tools
* social impact applications

---

# 🚀 System Overview

GemmaShield integrates three AI components into one unified pipeline:

1. 🎧 CNN-based voice spoof detection
2. 🗣 Whisper speech transcription
3. 🧠 Gemma 4 risk reasoning and explanation

The system performs:

* AI voice detection
* scam risk assessment
* explainable AI analysis
* real-time audio understanding

---

# ⚙️ Multimodal Pipeline

Audio Waveform
↓
16kHz Resampling
↓
Log-Mel Spectrogram
↓
CNN Spoof Detector
↓
Spoof Probability Score
↓
Whisper Transcription
↓
Gemma 4 Reasoning
↓
Human-readable Scam Risk Analysis

---

# 🧠 Core Features

* 🎧 Real-time AI voice scam detection
* 🧠 Gemma 4 explainable reasoning
* 🗣 Automatic speech transcription
* 📊 Spoof probability estimation
* ⚡ CPU-deployable lightweight pipeline
* 🌍 Designed for social good applications
* 📱 Deployable on edge or low-resource environments

---

# 🧱 Model Architecture

## CNN Spoof Detector

* Input: 64-bin Log-Mel Spectrogram
* 3-layer convolutional network
* BatchNorm + ReLU activation
* MaxPooling layers
* Fully connected classifier

Output:

* REAL probability
* SPOOF probability

---

# 📊 Audio Preprocessing

Each audio file is:

* converted to mono
* resampled to 16kHz
* normalized
* padded/truncated to fixed length
* transformed into log-mel spectrograms

This improves robustness under:

* noisy environments
* incomplete recordings
* real-world telecom audio conditions

---

# 🧠 Gemma 4 Reasoning Module

GemmaShield uses Gemma 4 for explainable telecom fraud analysis.

Gemma 4 analyzes:

* suspicious linguistic patterns
* emotional manipulation indicators
* impersonation risk
* scam-related conversational behavior

Example output:

> "The conversation shows indicators consistent with AI-generated telecom impersonation attempts and contains potential emotional manipulation patterns."

---

# 🚀 Live Demo

Hugging Face Space:

https://huggingface.co/spaces/Laura-smith/voice-spoof-detector

Features:

* Upload audio files
* Microphone recording
* Real-time spoof detection
* Speech transcription
* Gemma 4 risk analysis

---

# 📂 Project Structure

app.py                 # Gradio application
model.py               # CNN architecture
train.py               # Training pipeline
inference.py           # Inference pipeline
requirements.txt
README.md
best_model.pth

---

# ⚙️ Installation

```bash
pip install -r requirements.txt
```

---

# 🚀 Run Locally

```bash
python app.py
```

---

# 📊 Applications

GemmaShield can support:

* telecom anti-fraud systems
* scam call monitoring
* public safety AI tools
* elderly protection systems
* AI-generated media detection
* explainable AI security applications
* edge AI voice protection systems

---

# 🌍 AI for Social Good

This project aligns with Track D: AI for Social Good by addressing real-world public safety problems caused by rapidly advancing AI voice synthesis technologies.

GemmaShield focuses on:

* protecting vulnerable populations
* improving AI transparency
* reducing telecom fraud risks
* making AI safety tools more accessible

---

# 🏁 Summary

GemmaShield demonstrates:

✔ Multimodal AI integration
✔ Real-time voice scam detection
✔ Gemma 4 reasoning capabilities
✔ Explainable AI analysis
✔ Lightweight CPU deployment
✔ Social impact oriented AI system

---

# 📌 Author

Author: lwenxuan420

Built for: liuwenxuan
Gemma 4 Developer Competition 2026
Track D — AI for Social Good

---

# 📄 License

Academic and research use only.
