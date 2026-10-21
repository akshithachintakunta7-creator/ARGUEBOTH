# ArgueBoth

**Understand both sides. Decide for yourself.**

ArgueBoth is an AI-powered balanced debate helper that helps users understand multiple perspectives on controversial topics. Instead of giving a single verdict, it presents the strongest reasonable arguments for and against a topic, uncovers hidden assumptions, finds common ground, and suggests possible compromises.

## 🚀 Live Demo
https://akshithachintakunta7-creator.github.io/ARGUEBOTH/

## ✨ Features
- **Balanced Debates**: Generates arguments for and against any topic.
- **Steelman Mode**: Toggle this feature to force the AI to present the fairest, most persuasive version of the opposing view (rather than a strawman).
- **Common Ground Finder**: Identifies shared values between opposing sides.
- **Evidence Check**: Suggests what data or research would be needed to settle the debate (without inventing fake statistics).
- **Copy to Clipboard**: Easily save and share generated debates.
- **Responsible AI**: In-memory rate limiting prevents API abuse. No chat history is ever stored.

## 🛠️ Tech Stack
- **Frontend**: Plain HTML5, CSS3, and Vanilla JavaScript (hosted on GitHub Pages).
- **Backend Proxy**: Cloudflare Workers (Node.js environment).
- **AI Model**: Groq API (running `llama-3.3-70b-versatile`).

## 🏗️ Architecture
1. The user enters a topic on the static GitHub Pages frontend.
2. The frontend sends a `POST` request to the secure Cloudflare Worker.
3. The Worker injects the secret Groq API key, formats a strict JSON schema prompt, and forwards the request to Groq.
4. The AI generates the debate, and the Worker returns the JSON to the frontend for rendering.

## 💻 Local Development
1. Clone the repo.
2. Frontend: Open `index.html` with a local server (e.g., Live Server in VS Code).
3. Backend: Navigate to `backend/`, run `npm install`, and use `wrangler dev` to test the Worker locally. You will need a `.dev.vars` file containing `GROQ_API_KEY="your_key"`.

## 📝 Assignment Context
This project was built to demonstrate full-stack serverless architecture, advanced prompt engineering, and responsive UI design.