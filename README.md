# Anneal

> *From metallurgy — the process of heating and slowly cooling a material to relieve internal stress and reshape its structure without changing what it fundamentally is.*
>
> That's exactly what this does to text.

A recursive document humanization tool that rewrites AI-generated text through multiple passes of increasing context, refining until the content reads naturally — without changing what it's actually saying.

---

## The Problem

AI detectors don't just look for specific words. They look for patterns — sentence rhythm, structural predictability, the way ideas connect. A single rewrite pass rarely breaks all of those patterns at once. Anneal takes a different approach: start small, iterate, expand, repeat — until the document stops reading like a machine wrote it.

---

## How It Works

```
Input text
↓
Split into sentences
↓
Rewrite sentence by sentence (smallest context)
↓
Score with local detection model
↓
Expand context window, rewrite again
↓
Score again
↓
Repeat, expanding context each iteration
↓
Final verification against real detector API
↓
Output when score drops below threshold
```

---

## Features

- Recursive rewriting loop with expanding context windows
- Local AI detection model for fast, free iterative scoring
- Final verification pass against a real detection API
- Format and structure preservation — only the prose is touched
- Configurable score threshold (default: 25%)
- Plain text input to start, file format support planned

---

## Stack

- **Language** — Python
- **Rewriting** — LLM API (Anthropic / OpenAI)
- **Loop Scoring** — Local open source detection model
- **Final Verification** — GPTZero or Originality.ai API

---

## Status

🔲 Rewriter — single paragraph rewrite via LLM API  
🔲 Chunker — sentence splitting and reassembly  
🔲 Scorer — local model integration  
🔲 Loop — recursive refinement orchestrator  
🔲 Verifier — final detection API check  
🔲 CLI — simple command line interface  

---

## Ground Rules

- The document's ideas, arguments, and information are never changed
- Only phrasing, rhythm, and sentence structure are reshaped
- Each component is built and tested independently before being wired together

---

## Disclaimer

This tool is built as a technical exercise in NLP, recursive systems, and LLM API integration. Use responsibly and in accordance with your institution's academic policies.
