# Generative-AI-Transformers-Discovery
This will explore state-of-the-art pre-trained language models using Python and the HuggingFace `transformers` library.This project strengthens the leverage modern NLP tools while understanding their operational and ethical constraints using the Discovery-to-Action (DTA) framework.
# Generative AI & Transformers Pipeline: Text Analysis & Generation

An enterprise-ready NLP pipeline utilizing the Hugging Face `transformers` API and PyTorch to automate text triage, generation, and summary processing within a stateful **Discovery-to-Action (DTA)** framework.

## Pipeline Configurations

This project evaluates the out-of-the-box performance boundaries of three baseline architectures via high-level pipeline abstractions:
1. **Sentiment Analysis:** Configured with `distilbert-base-uncased-finetuned-sst-2-english` for immediate textual tone classification.
2. **Text Generation:** Initialized with `gpt2` to explore causal autoregressive word-prediction sequences.
3. **Summarization:** Managed via `distilbart-cnn-12-6` to test information density distillation.

## Core Findings & Nuance Audit

* **The Sarcasm Vulnerability:** Initial testing proves that vanilla sentiment models fail to detect contextual irony, incorrectly tracking phrase payloads with heavy sarcasm as positive based purely on literal word usage.
* **Generation Trailing:** Text generation outputs under strict constraints (`max_length=50`) illustrate structural cutoff challenges, confirming the necessity of parsing tools or stop-token sequences in customer-facing code.

## Production Triage Strategy (1,000 tickets/day)

To automate large-scale customer queues efficiently, the modules are designed as an integrated pipeline:
1. **Sentiment Triage:** Identifies high-anger scores to escalate tickets directly to senior support teams.
2. **Summarization Compression:** Distills wordy tickets into clean metadata summaries for agents.
3. **Draft Synthesis:** Employs generation layers to pre-populate custom contextual responses, allowing support teams to review and send answers instantly, reducing typing overhead.

## Setup Requirements
```bash
pip install transformers torch sentencepiece
