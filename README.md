# 🛡️ GemmaShield
![Demo](demo.png)
# Protecting Elderly Users from AI Voice Scams with Explainable AI

[English](#english) | [简体中文](#简体中文)

An AI-powered multimodal scam detection system that combines:

- Voice Spoof Detection
- Speech Recognition
- Large Language Model Reasoning
- Explainable AI Safety Analysis

to help elderly users identify increasingly sophisticated AI-generated scam calls.

Built with Google Gemma 4.

---

## 🌍 Why GemmaShield Matters
![picture](picture.png)
AI voice cloning technology is rapidly becoming accessible.

Today, scammers can generate highly realistic voices that imitate:

- family members
- friends
- government agencies
- bank representatives

with only a few seconds of recorded speech.

Older adults are particularly vulnerable to these attacks because:

- they often trust familiar voices
- they may have limited experience with AI-generated media
- voice-based scams frequently create urgency and emotional pressure

Unfortunately, most existing voice spoof detection systems only provide a probability score.

For non-technical users, outputs such as:

```text
Fake Probability: 0.82
```

do not explain:

- Why is this suspicious?
- What should I do next?
- How serious is the risk?

GemmaShield was created to bridge this gap.

Instead of functioning solely as an AI classifier, GemmaShield acts as an AI safety assistant capable of explaining risks in human language.

---

# 🎯 Project Goals

GemmaShield aims to:

- Detect AI-generated fake voices
- Identify potential telecom fraud indicators
- Provide understandable explanations
- Assist elderly users in making safer decisions
- Explore robustness challenges in real-world deployment
- Study trustworthy AI systems for social good

---

# 🤖 Why Gemma 4

Traditional spoof detection systems stop at classification.

GemmaShield integrates Google Gemma 4 to transform detection results into actionable safety guidance.

Gemma 4 is used for:

- Scam transcript analysis
- Risk reasoning
- Fraud indicator detection
- Elderly-friendly explanation generation
- Bilingual communication support

This transforms the system from:

```text
Voice Classifier
```

into:

```text
Voice Safety Assistant
```

---

# 🏗 System Architecture
![Architecture](architecture.png)
```text
Audio Input
      │
      ▼
CNN Voice Spoof Detection
      │
      ▼
Faster-Whisper Speech Recognition
      │
      ▼
Gemma 4 Reasoning Engine
      │
      ▼
Explainable Scam Assessment
      │
      ▼
Elderly-Friendly Safety Advice
```

---

# ⚙️ Core Technologies

| Component | Technology |
|------------|------------|
| Voice Spoof Detection | CNN |
| Speech Recognition | Faster-Whisper |
| AI Reasoning | Google Gemma 4 |
| Frontend | Gradio |
| Deployment | Hugging Face Spaces |
| Audio Features | Log-Mel Spectrogram |

---

# 🔬 Voice Spoof Detection Research

A major focus of this project is understanding the gap between laboratory performance and real-world deployment.

---

## Training Dataset

Initial training used:

- ASVspoof Dataset
- Approximately 110,000 training samples

---

## Benchmark Performance

The CNN model achieved:

```text
EER ≈ 0.00134
```

on clean benchmark data.

This indicates extremely strong laboratory performance.

---

# ⚠️ Real-World Deployment Challenge

To evaluate practical robustness, we collected approximately:

```text
100 real-world audio samples
```

including:

- phone call recordings
- replay attacks
- compressed speech
- microphone variations
- noisy environments
- AI-generated voices

Direct evaluation revealed:

```text
EER ≈ 0.30
```

This demonstrated a severe domain gap between benchmark datasets and real-world audio.

---

# 📊 EER Comparison
![EER](eer_chart.png)
| Dataset | EER |
|----------|----------|
| ASVspoof Benchmark | 0.00134 |
| Real-world Dataset | 0.30 |
| Augmented Dataset | 0.03 |

---

# 🔬 Data Augmentation Study
![Augmentation](augmentation.jpg)

To address the limited size of real-world data, a custom augmentation pipeline was developed.

The original dataset of approximately:

```text
100 samples
```

was expanded into:

```text
50,000 augmented samples
```

using:

- Noise Injection
- Pitch Shifting
- Replay Simulation
- Frequency Perturbation
- Audio Distortion
- Waveform Modification

Metadata and labels were synchronized automatically.

---

# 🧠 Transfer Learning Strategy

Instead of retraining from scratch:

1. ASVspoof-pretrained CNN was retained
2. Early layers were frozen
3. Remaining layers were fine-tuned
4. Augmented real-world data was used for adaptation

Result:

```text
EER ≈ 0.03
```

---

# 🔍 Key Research Finding

One of the most important discoveries of this project was:

> Extremely low benchmark EER does not guarantee real-world robustness.

Although fine-tuning improved validation performance, additional testing revealed:

- improved recognition of genuine speech
- reduced generalization to unseen spoof attacks

This suggests that the model may learn characteristics of "realness" rather than generalized spoof patterns.

This finding highlights an important challenge for future AI security research.

---

# 🔄 Current Deployment Strategy

Because robustness remains a critical challenge, the deployed system currently uses:

- ASVspoof-trained CNN
- stable inference pipeline
- conservative deployment strategy

Future robustness research continues separately.

---

# 🧠 Explainable AI with Gemma 4
![Gemma Analysis](gemma_reasoning.jpg)
Gemma 4 receives:

- Speech transcript
- Spoof probability
- Contextual scam indicators

and generates explanations such as:

```text
Potential Scam Detected

Risk Level: Medium

Reason:
The caller requests urgent financial action
while claiming to be a family member.

Recommendation:
Verify identity through another communication channel
before sending money.
```

This makes detection results understandable for elderly users.

---

# 👵 Elderly-Friendly Design

GemmaShield is specifically designed for older adults.

Features include:

- Large fonts
- Simple interaction flow
- Chinese / English support
- Readable AI explanations
- Clear risk categories
- Actionable recommendations

The objective is not only detection accuracy, but user understanding.

---

# 🚀 Features

✅ Voice Spoof Detection

✅ Scam Risk Analysis

✅ Faster-Whisper Transcription

✅ Gemma 4 Reasoning

✅ Explainable AI

✅ Elderly-Friendly Interface

✅ Chinese / English Support

✅ Hugging Face Deployment

✅ Real-Time Audio Upload

---

# 🌍 Social Impact

GemmaShield addresses a growing societal challenge:

AI-generated voice scams targeting vulnerable populations.

The project contributes to:

- AI Safety
- Elderly Protection
- Digital Trust
- Explainable AI
- Responsible AI Deployment

As voice cloning technology becomes increasingly powerful, systems capable of explaining risks may become an important component of future digital safety infrastructure.

---

# ⚠️ Current Limitations

Current limitations include:

- Real-world spoof detection remains challenging
- Unseen attack types may reduce performance
- Background noise may affect transcription quality
- Scam assessment should assist, not replace, human judgment

---

# 🔮 Future Work

Future directions include:

- Real-time phone call protection
- Streaming audio analysis
- Edge-device deployment
- Multilingual scam detection
- Adversarial spoof defense
- Improved robustness training
- Function Calling integration with Gemma 4

---

# 📁 Project Structure

```text
GemmaShield/
│
├── app.py
├── model.py
├── train.py
├── inference.py
├── best_model.pth
├── requirements.txt
├── fake_data/
├── real_data/
├── architecture.png
├── eer_chart.png
├── demo.png
├── technical_report.pdf
├── demo_video.mp4
└── README.md
```

---

# 👨‍💻 Author

Developed by a Computer Science student exploring:

- AI Security
- AI Safety
- Voice Trustworthiness
- Human-Centered AI
- Explainable AI
- Multimodal AI Systems

---

# 📄 License

This project is intended for research and educational purposes.

MIT License.
