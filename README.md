🎯 AI & Data Quest

A clean, distraction-free to-do app with an AI brain-dump organizer and a GitHub-style consistency heatmap.

I wanted a simple to-do app, but every one I tried came with ads, subscriptions, or a hundred features I never used. So I built my own: no login, no ads, no paywall.

🔗 Live demo: https://ramya63822.github.io/ai-quest-todo/

<!-- Add a screenshot: save it as screenshot.png in the repo and uncomment the line below --> <!-- ![App screenshot](screenshot.png) -->
✨ Features
AI brain dump: type your messy thoughts (for example, "practise DSA, do laundry, then learn about transformers") and Gemini turns them into a clean checklist
Hype Me Up: a short, personalised motivational message based on what you've finished today
Contribution heatmap: a 12-week view of your completed tasks, with today highlighted and hover tooltips
Daily streak counter: counts consecutive days with at least one completed task
Daily reset: checkboxes reset each day while your history is kept
Two themes: Obsidian (dark) and Pink, with animated background particles
Personalise: editable workspace title and custom avatar upload
Private by design: all data lives in your browser's localStorage, with no backend and no account
🚀 Getting started
Run locally
bash
git clone https://github.com/ramya63822/ai-quest-todo.git
cd ai-quest-todo

Then open index.html in your browser. There is nothing to install or build.

Enable the AI features

The to-do list, heatmap and streak work without any setup. The AI buttons need your own free Gemini API key:

Get a key from Google AI Studio
Click the 🔑 icon in the app header and paste the key
Type a brain dump and hit Organize Thoughts

Your key is stored only in your browser and is sent only to Google's Gemini API. It is never part of this repository.

🧠 How the AI part works
Requests go straight from the browser to the Gemini generateContent endpoint
The default model is gemini-3.5-flash-lite, which is small and fast enough for turning text into tasks
If it is busy, the app retries with short back-off and then falls back to gemini-3.8-flash
The prompt tells the model to use only what you wrote and return a JSON array of short tasks
Model names are constants at the top of the AI section in index.html (GEMINI_MODEL, GEMINI_FALLBACK_MODEL), so you can swap them easily
🛠️ Tech stack
HTML, CSS and vanilla JavaScript (single file)
Tailwind CSS (CDN build)
Lucide icons
Google Gemini API
localStorage for persistence
🌐 Deploy your own copy

It's a single static file, so GitHub Pages works out of the box:

Fork or upload this repo to your GitHub account
Go to Settings → Pages
Under Source, choose Deploy from a branch, then select main and / (root)
Save. Your site will be live at https://<your-username>.github.io/<repo-name>/ in about a minute
🤝 Contributing

It's a small personal project, but ideas and PRs are welcome. Fork it, make it yours, and open an issue if you have a suggestion.

📄 License

MIT. Use it, fork it, change it freely.
