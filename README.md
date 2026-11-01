# AI Video Detector

A browser extension that detects AI-generated videos on TikTok and Facebook and labels them with a confidence score as you scroll.

**Author:** Ngoc Vu

## Project Goal

Lately, AI video generation has grown significantly, making it difficult for people to distinguish AI-generated videos from authentic ones. While some are made for entertainment, others take the form of scam fundraising appeals. As manipulated scenes can spread misinformation and exploit human trust, a tool to detect fake videos while browsing social media would be useful for those who value authenticity, and help protect people from scams and fraud.

Therefore, I'm working on a project to build a Chrome extension that detects AI-generated videos, with backend services and an inference pipeline. I will train a deep learning model for detection using the GenVideo-100K dataset from the 2024 DeMamba benchmark paper. I plan to use Docker to containerize it and integrate Redis for asynchronous task processing and result caching. The ML code will use the PyTorch framework, while the front end uses Figma, TypeScript, and CSS.

## MVP Scope

- **Detection model:** a pretrained video/image model fine-tuned on GenVideo-100K to classify real vs. AI-generated videos
- **Inference API:** a backend endpoint that takes video frames and returns an "AI-generated" probability
- **Frame capture:** a browser extension that captures frames from TikTok/Facebook videos as the user scrolls

## Future Plans (V2.0+)

- Extend to other platforms (YouTube, Instagram, ...)
- A stronger model that generalizes to newer AI video generators
- Evidence of why a video looks AI-generated (explainability for the black-box model)

## Tech Stack

| Layer | Tools |
|---|---|
| Model | Python, PyTorch, Hugging Face Transformers and Datasets |
| Backend | FastAPI, Redis, Docker |
| Frontend | TypeScript/JavaScript, CSS (browser extension) |

## Repository Structure

```
ai-video-detector/
├── model/
├── backend/
├── extension/
├── tests/
├── docs/
├── docker-compose.yml
└── README.md
```
