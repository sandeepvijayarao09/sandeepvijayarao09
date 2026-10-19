# Sandeep Vijayarao

**ML engineer working on on-device language models, and on the evaluations that show what actually works.**

I train and fine-tune small models, run them on phones and laptops, and measure them carefully, including when the answer is "this didn't help." MS CS at Northeastern (May 2027). Apple Swift Student Challenge 2026 winner.

[Portfolio](https://sandeepvijayarao09.github.io) · [LinkedIn](https://www.linkedin.com/in/sandeepvijayarao/) · sandeepvijayarao09@gmail.com

---

## Selected work

**[DeviceControlSlm](https://github.com/sandeepvijayarao09/DeviceControlSlm)**: a small language model for on-device phone and Mac control
- I trained a ~4.1M-parameter transformer from scratch (my own architecture, tokenizer and weights) and compared it with LoRA-tuned Qwen2.5-0.5B on DeviceControlBench, a benchmark I built.
- **Result:**
  - Familiar phrasing (in-distribution): the scratch model wins, 67.2% vs 51.6%.
  - New phrasing (held out): it falls to 32.7%, below the fine-tuned Qwen's 36.4%.
  - The pretrained model generalizes better.
- **Method:** a held-out phrasing split, a train/test contamination gate, confidence intervals, and a confirmation gate that kept the unsafe-execution rate at 0% for every model.
- `PyTorch` `LoRA` `MLX` `Core ML` `App Intents`

**[RAG From Scratch](https://github.com/sandeepvijayarao09/rag-from-scratch)**: ten retrieval techniques, each measured on BEIR SciFact (nDCG@10)
- **Result:** seven of the ten made retrieval worse. Only two helped:
  - weighted hybrid search: +0.010
  - cross-encoder reranking on top of BM25: +0.041
- **Method:** I checked the baseline (`bge-base`, 0.759) against a published figure before building anything on it.
- CRAG-style document grading scored 0.50 balanced accuracy, which is chance level.
- `Python` `BEIR` `bge` `cross-encoders` · [interactive guide](https://sandeepvijayarao09.github.io/RAG/)

**[Anu](https://github.com/sandeepvijayarao09/Anu-iOS)**: an on-device agent for iOS, and the Swift Student Challenge 2026 winner
- Gemma 4 E4B runs locally through LiteRT.
- An on-device router (NLEmbedding nearest-centroid) picks the task type, model and tools for each message. It scores 91.7% on a 60-case eval.
- It reaches the cloud only as an optional fallback, with personal information scrubbed first.
- 317 unit tests run in CI.
- `Swift 6` `LiteRT` `Gemma` `ReAct`

**[NeuroRecursion](https://github.com/sandeepvijayarao09/neurorecursion)**: agents that keep a frozen brain-computer-interface (BCI) decoder usable across days without new labels (Crusoe × Cerebral Valley hackathon, Oct 2026)
- Tested on real recordings from human BCI users (FALCON H1), over 7 held-out days.
- With no labels, the agents beat the frozen decoder on 6 of 7 days: mean velocity R² −0.016 vs −0.062.
- Few-shot recalibration, which does need labels, still does better at +0.106.
- `Python` `Nemotron` `Crusoe Inference`

**[Dual LLM Router](https://github.com/sandeepvijayarao09/dual-llm-system)**: a cascade router that decides whether each query goes to GPT-4o-mini or GPT-4o
- The router scores 92.6% routing accuracy.
- My follow-up ablation found that a one-line word-count rule gets 89.7%, and the confidence intervals overlap.
- Almost all of the router's gain comes from length features. The cause is a benchmark artifact, documented in FINDINGS.md.
- `scikit-learn` `OpenAI`

**[meeting-bot](https://github.com/sandeepvijayarao09/meeting-bot)**: a local-first meeting notetaker for macOS
- Whisper transcribes on-device, with speaker attribution, so no audio leaves the Mac.
- Ships as a signed release with a SwiftUI app, a CLI and a Chrome extension.
- `Whisper` `SwiftUI` `Python`

### More projects

**On-device apps**

| Project | What it is |
|---|---|
| [Anu for Android](https://github.com/sandeepvijayarao09/Android_ANU) | The Android version of Anu, a private assistant that runs on the phone (Kotlin) |
| [Notova for iPhone and Mac](https://github.com/sandeepvijayarao09/notova-ios) | Records voice notes, then transcribes and summarizes them on the device (Apple Speech, Foundation Models, MLX Gemma) |
| [Notova for Android](https://github.com/sandeepvijayarao09/notova-android) | The same app on Android, using Gemma 3n through LiteRT-LM and Gemini Nano |
| [Autodoc](https://github.com/sandeepvijayarao09/Autodoc) | A macOS menu-bar app that keeps a running work log for each project, using a local Gemma vision model |

**AI tools**

| Project | What it is |
|---|---|
| [Agent-Certifier](https://github.com/sandeepvijayarao09/Agent-Certifier) | A security scanner for AI-agent code: 60 checks, mapped to the OWASP Agentic and LLM Top 10 |
| [autofill-pro](https://github.com/sandeepvijayarao09/autofill-pro) | A Chrome extension that fills job applications in one click: 44 profile fields, tested on 46 job sites and applicant-tracking systems |

**Hackathons**

| Project | What it is |
|---|---|
| [Omni-Axon](https://github.com/sandeepvijayarao09/Omni-Axon) | Built at the Stanford x DeepMind hackathon. A Gemini orchestrator that routes each request to a direct answer, a saved multi-agent workflow, or a new agent team |
| [omniq-atlas](https://github.com/sandeepvijayarao09/omniq-atlas) | Built at the SFTW Harness Engineering hackathon. A governed AI assistant for organizations, on MongoDB Atlas, whose harness improves itself |

---

## Background

- **AI Developer, Trominosoft** (2025): LLM orchestration and retrieval services on GCP and Kubernetes
- **Graduate TA, Northeastern** (Computer Vision, Generative AI)
- **AI Intern, Infosys Springboard** (2024): quantized 7B-model serving with vLLM
- **Publication:** co-author, *Real-Time Human Pose Estimation Using MediaPipe*, IEEE AISP 2024

**Tools I use most:** PyTorch · Hugging Face · LoRA/PEFT · vLLM · MLX · LiteRT · Core ML · Swift · Kotlin · Python
