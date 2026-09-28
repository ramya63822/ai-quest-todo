# 🎯 AI & Data Quest

A clean, distraction-free to-do app featuring an AI brain-dump organizer and a GitHub-style consistency heatmap.

I wanted a simple to-do app, but every one I tried came with ads, subscriptions, or a hundred features I never used. So I built my own: no login, no ads, no paywall.

🔗 **Live demo:** [https://ramya63822.github.io/ai-quest-todo/](https://ramya63822.github.io/ai-quest-todo/)

## ✨ Features

*   🧠 **AI Brain Dump:** Type your messy thoughts (for example, "practise DSA, do laundry, then learn about transformers") and Gemini turns them into a clean checklist.
*   🔥 **Hype Me Up:** A short, personalized motivational message based on what you've finished today.
*   **Contribution Heatmap:** A 12-week view of your completed tasks, with today highlighted and hover tooltips.
*   **Daily Streak Counter:** Counts consecutive days with at least one completed task.
*   **Daily Reset:** Checkboxes reset each day while your history is kept.
*   **Two Themes:** Obsidian (dark) and Pink, complete with animated background particles.
*   **Personalize:** Editable workspace title and custom avatar upload.
*   **Private by Design:** All data lives in your browser's localStorage, with no backend and no account required.

## 🚀 Getting Started

### Run Locally
```bash
git clone https://github.com/ramya63822/ai-quest-todo.git
cd ai-quest-todo
```
Then open `index.html` in your browser. There is nothing to install or build!

### Enable the AI Features
The to-do list, heatmap, and streak work without any setup. The AI buttons need your own free Gemini API key:
1. Get a key from Google AI Studio.
2. Click the 🔑 icon in the app header and paste the key.
3. Type a brain dump and hit **Organize Thoughts**.

*Note: Your key is stored only in your browser and is sent solely to Google's Gemini API. It is never part of this repository.*

## 🧠 How the AI Part Works
*   Requests go straight from the browser to the Gemini `generateContent` endpoint.
*   The default model is `gemini-3.5-flash-lite`, which is small and fast enough for turning text into tasks.
*   If it is busy, the app retries with short back-off and then falls back to `gemini-3.8-flash`.
*   The prompt tells the model to use only what you wrote and return a JSON array of short tasks.
*   Model names are constants at the top of the AI section in `index.html` (`GEMINI_MODEL`, `GEMINI_FALLBACK_MODEL`), so you can swap them easily.

## 🛠️ Tech Stack
*   HTML, CSS, and Vanilla JavaScript (single file)
*   Tailwind CSS (CDN build)
*   Lucide Icons
*   Google Gemini API
*   localStorage for data persistence

## 🌐 Deploy Your Own Copy
It's a single static file, so GitHub Pages works right out of the box:
1. Fork or upload this repo to your GitHub account.
2. Go to **Settings** → **Pages**.
3. Under **Source**, choose **Deploy from a branch**, then select **main** and **/ (root)**.
4. Click **Save**.

Your site will be live at `https://<your-username>.github.io/<repo-name>/` in about a minute!

## 🤝 Contributing
It's a small personal project, but ideas and PRs are welcome. Fork it, make it yours, and open an issue if you have a suggestion.

## 📄 License
MIT. Use it, fork it, change it freely.

---
Built by Ramyaa · [LinkedIn](https://www.linkedin.com/in/ramyasreesv/)
