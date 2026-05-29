# 🛡 GemmaShield
## AI Voice Scam Detection System for Elderly Protection

GemmaShield is an AI-powered voice scam detection system designed to help elderly users identify spoofed or potentially fraudulent voice calls.

The project combines:

- 🎤 Voice spoof detection (CNN)
- 🗣 Speech transcription (Whisper)
- 🧠 Large Language Model reasoning (Gemma4)
- 👵 Elderly-friendly UI design
- 🔒 AI safety and scam prevention

This project was developed as an exploration of real-world AI security, voice trustworthiness, and multimodal AI reasoning systems.

---

# 🌟 Project Motivation

With the rapid development of AI voice cloning technologies, elderly users are becoming increasingly vulnerable to:

- AI-generated scam calls
- Fake family voice impersonation
- Financial fraud
- Emotional manipulation attacks

Most existing spoof detection research focuses on benchmark datasets and laboratory conditions.

However, real-world voice environments are significantly more complex.

GemmaShield explores:

> Can AI systems detect spoofed voices in real-world conditions while also helping elderly users understand the risks through natural language explanations?

---

# 🧠 System Architecture

The system uses a dual-stage AI pipeline:

```text
Audio Input
    ↓
CNN Voice Spoof Detection
    ↓
Whisper Speech Recognition
    ↓
Gemma4 Risk Reasoning
    ↓
Human-readable Scam Analysis
```

---

# ⚙️ Core Technologies

## 1. CNN Voice Spoof Detection

The spoof detection model is based on a CNN architecture trained on spectrogram features.

### Training Dataset

The model was first trained on:

- ASVspoof dataset
- Approximately 110,000 clean training samples

### Initial Performance

The CNN achieved:

```text
EER ≈ 0.00134
```

on clean benchmark data.

This demonstrated extremely strong performance under laboratory conditions.

---

# ⚠️ Real-World Dataset Problem

Although the model performed well on ASVspoof benchmark data, it struggled with real-world audio.

To investigate this issue, we manually collected approximately:

```text
100 real-world audio samples
```

including:

- phone recordings
- noisy environments
- compressed audio
- microphone variations
- real human speech
- replayed fake speech

However, because the dataset was too small, direct training produced poor results:

```text
EER ≈ 0.30
```

This revealed a major domain gap between laboratory data and real-world audio.

---

# 🔬 Data Augmentation Research

To address the lack of real-world data, we developed a custom augmentation pipeline.

The original 100 samples were expanded to approximately:

```text
50,000 augmented audio samples
```

using techniques such as:

- noise injection
- pitch shifting
- frequency modification
- waveform perturbation
- audio distortion
- replay simulation

Additionally:

- a custom CSV metadata system was generated
- labels were automatically expanded alongside the audio dataset

---

# 🧠 Transfer Learning Strategy

Instead of training from scratch, we reused the CNN trained on the 110k ASVspoof dataset.

We then:

- froze part of the CNN layers
- fine-tuned the remaining layers
- trained on the augmented 50k real-world dataset

This transfer learning strategy significantly improved performance.

### Fine-tuned Result

```text
EER ≈ 0.03
```

This was a major improvement compared to the earlier real-world training attempt.

---

# ⚠️ Robustness Problem Discovery

Although the fine-tuned model achieved a lower EER during validation, further real-world testing revealed an important issue.

When testing carefully selected real-world samples:

- the model became very good at recognizing genuine speech
- but struggled to identify spoofed real-world fake voices

This suggested that the model had begun overfitting to specific real-world characteristics.

In other words:

> the model learned to recognize “realness” rather than truly learning generalized spoof detection.

This became one of the most important findings of the project.

---

# 🔍 Current Research Direction

After identifying the robustness issue, we decided to:

- remove the problematic real-world fine-tuning stage
- return to the cleaner ASVspoof-trained model
- continue investigating robustness improvements

The current deployed model is therefore based primarily on the original ASVspoof-trained CNN.

Future research directions include:

- robustness optimization
- domain adaptation
- noisy environment generalization
- replay attack resistance
- real-world spoof robustness
- multilingual spoof detection

---

# 🧠 Gemma4 Integration

GemmaShield integrates:

## Google Gemma4

to provide natural-language scam reasoning.

The LLM analyzes:

- speech transcripts
- spoof probability
- contextual scam indicators

and generates explanations such as:

```text
Scam: Possible
Risk: Medium
Advice: Do not share personal information or banking details.
```

This transforms the system from:

```text
"AI classifier"
```

into:

```text
"AI safety assistant"
```

---

# 👵 Elderly-Friendly Design

Because the project specifically targets elderly users, the interface was designed with accessibility in mind.

Features include:

- large fonts
- simplified buttons
- bilingual support (Chinese / English)
- easy-to-understand AI explanations
- minimal interaction complexity

The goal is not only detection accuracy, but also:

> helping elderly users understand why a voice may be dangerous.

---

# 🎤 Speech Recognition

The system uses:

## Faster-Whisper

for lightweight CPU-based speech transcription.

Whisper converts uploaded audio into transcripts before sending the text to Gemma4 for reasoning.

---

# 🚀 Features

- ✅ Voice spoof detection
- ✅ AI scam reasoning
- ✅ Real-time audio upload
- ✅ Whisper speech recognition
- ✅ Gemma4 explanation system
- ✅ Elderly-friendly interface
- ✅ Dual-language support
- ✅ CPU-compatible deployment
- ✅ HuggingFace Spaces support

---

# 🌐 Online Demo

## HuggingFace Space

👉 Demo Link:

https://huggingface.co/spaces/Laura-smith/voice-spoof-detector

The online demo supports:

- 🎤 Voice upload
- ⚡ Real-time spoof detection
- 🗣 Whisper transcription
- 🧠 Gemma4 AI reasoning
- 👵 Elderly-friendly interface
- 🌐 Chinese / English support

To ensure deployment stability under limited HuggingFace CPU memory:

- Gemma4 uses lazy loading
- Whisper uses lightweight tiny mode
- CPU-safe inference optimization is enabled

---

# 📊 Example Output

```text
✅ SAFE

Real Voice Score: 0.97
Fake Voice Score: 0.03

Transcript:
"Hello, this is your grandson..."

AI Analysis:
Scam: Possible
Risk: Medium
Advice: Verify the caller identity before sending money.
```

---

# 📦 Competition Submission Materials

This project submission includes:

## ✅ Source Code Repository

Complete GitHub / HuggingFace source code repository including:

- app.py
- model.py
- training pipeline
- inference pipeline
- augmentation scripts
- deployment configuration
- README documentation

---

## ✅ 5-Minute Demonstration Video

The demo video includes:

- project motivation
- real-world scam problem introduction
- model architecture explanation
- live spoof detection demo
- Gemma4 reasoning demonstration
- elderly-friendly interface showcase
- robustness discussion
- future work directions

---

## ✅ Technical Report

The technical report includes:

- dataset construction
- ASVspoof training process
- real-world data collection
- augmentation strategy
- transfer learning experiments
- EER comparison analysis
- robustness discussion
- deployment optimization
- Gemma4 integration design

---

## ✅ Online Interactive Demo

Interactive deployment is available through HuggingFace Spaces:

https://huggingface.co/spaces/Laura-smith/voice-spoof-detector

Users can directly upload audio files and test the system online.

---

# 🏆 Evaluation Criteria

The project was designed according to the official competition judging dimensions.

---

## 🌍 Real-world Impact (30%)

GemmaShield focuses on a highly realistic and increasingly important social problem:

> AI-generated voice scams targeting elderly users.

The system emphasizes:

- practical deployment
- elderly accessibility
- explainable AI interaction
- future scalability
- social impact

Unlike purely benchmark-focused projects, this project explicitly studies:

- robustness
- domain gap
- real-world deployment limitations

---

## ⚙️ Technical Excellence (25%)

The system integrates multiple AI technologies into a unified pipeline:

- CNN spoof detection
- Whisper ASR
- Gemma4 reasoning
- transfer learning
- augmentation pipeline
- HuggingFace deployment optimization

Technical highlights include:

- EER optimization
- real-world augmentation research
- partial CNN layer freezing
- lazy-loading LLM architecture
- CPU-safe deployment design

Gemma4 is deeply integrated rather than simply appended.

It actively performs:

- transcript understanding
- scam reasoning
- elderly-oriented explanation generation

---

## ✅ Functional Completeness (20%)

The system includes a complete runnable demo with:

- upload support
- real-time detection
- transcript generation
- AI reasoning
- bilingual UI
- runtime feedback
- HuggingFace deployment

Edge-case handling includes:

- no speech detection
- delayed Gemma loading
- CPU-only environments
- memory optimization

---

## 💡 Innovation (15%)

Key innovations include:

- combining spoof detection with LLM reasoning
- elderly-oriented AI explanation design
- robustness-focused experimentation
- real-world domain gap analysis
- multimodal AI security architecture

The project intentionally investigates failure cases and robustness limitations instead of only reporting benchmark success.

This became one of the most important research findings.

---

## 🎬 Presentation Quality (10%)

The project includes:

- detailed technical documentation
- complete README
- organized repository structure
- online deployment
- interactive demo
- professional presentation video

Special effort was also made to improve usability and readability for non-technical users and elderly audiences.

---

# 🖥 Local Deployment

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Run Application

```bash
python app.py
```

Then open:

```text
http://127.0.0.1:7860
```

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
│
├── data/
├── augmented_data/
├── csv/
└── README.md
```

---

# 📚 Research Significance

This project explores several important AI research topics:

- AI Security
- Voice Spoof Detection
- AI Safety
- Human-centered AI
- Robustness Research
- Multimodal AI Systems
- Elderly-oriented AI Applications

The project demonstrates that:

> achieving low benchmark EER alone is not sufficient for real-world deployment.

Robustness and real-world generalization remain critical challenges for future AI security systems.

---

# 🔬 Important Research Findings

One of the most important discoveries during this project was:

> Extremely low EER on benchmark datasets does not guarantee real-world robustness.

Even after improving real-world EER from:

```text
0.30 → 0.03
```

the model still struggled to generalize to unseen real-world fake voices.

This revealed that:

- robustness is more important than benchmark accuracy
- domain adaptation remains a major challenge
- real-world spoof detection is still an open research problem

This insight became a central research direction for the future development of GemmaShield.

---

# 🔮 Future Work

Future improvements may include:

- stronger robustness training
- adversarial spoof detection
- multilingual scam analysis
- emotional manipulation detection
- edge-device optimization
- real-time phone call protection
- streaming voice analysis

---

# ❤️ Social Impact

GemmaShield was designed with a social-good motivation:

> using AI to help protect elderly users from increasingly sophisticated AI voice scams.

As AI-generated voices become more realistic, systems like GemmaShield may play an important role in future digital safety infrastructure.

---

# 👤 Author

Developed by a first-year Computer Science student exploring:

- AI Security
- Voice Trustworthiness
- AI Safety Systems
- Human-centered AI

---

# 📄 License

This project is intended for research and educational purposes.
````
