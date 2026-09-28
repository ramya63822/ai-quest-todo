# 🎯 AI & Data Quest

> **An AI-powered, local-first productivity dashboard that turns messy thoughts into actionable tasks.**

I wanted a simple to-do app without ads, subscriptions, accounts, or features I would never use — so I built my own.

**AI & Data Quest** combines an AI-powered brain dump organizer with task tracking, productivity analytics, daily streaks, and a GitHub-style contribution heatmap.

No login. No backend. No ads. No paywall.

### 🔗 Live Demo

**[AI & Data Quest](https://ramya63822.github.io/ai-quest-todo/)**

---

## ✨ Features

### 🧠 AI Brain Dump

Turn unstructured thoughts into a clean checklist using Google Gemini.

For example:

```text
Practise DSA, finish my assignment, do laundry, then learn transformers
```

becomes:

```text
☐ Practise DSA
☐ Finish assignment
☐ Do laundry
☐ Learn about transformers
```

The AI is instructed to work only with the information provided and return structured JSON that the application converts into tasks.

### 🔥 Hype Me Up

Get a short personalized motivational message based on the tasks you've completed during the day.

### 📊 Productivity Heatmap

A GitHub-style **12-week contribution heatmap** visualizes your completed tasks.

* Today is highlighted
* Hover over days to view task activity
* Helps visualize consistency over time

### 🔥 Daily Streak

Automatically tracks consecutive days where at least one task was completed.

### 🌅 Daily Reset

Incomplete checkboxes reset each day while your historical activity remains available for the heatmap and streak system.

### 🎨 Two Themes

Choose between:

* **Obsidian** — dark theme
* **Pink** — colorful theme

Both include animated background particles.

### 👤 Personalization

Customize your workspace with:

* Editable workspace title
* Custom avatar
* Theme selection

### 🔒 Private by Design

Your tasks and settings are stored locally in your browser using:

```text
localStorage
```

There is no application backend or user account.

---

# 🤖 How the AI Works

The AI functionality runs directly in the browser.

```text
User Brain Dump
       ↓
JavaScript
       ↓
Gemini API
       ↓
Structured JSON
       ↓
Task Parser
       ↓
To-Do List
```

### Request Flow

1. The user enters an unstructured brain dump.
2. JavaScript sends the text directly to Google's Gemini API.
3. A structured prompt instructs the model to return a JSON array containing short actionable tasks.
4. The response is parsed by the application.
5. The generated tasks are added to the user's checklist.

### Model Configuration

The Gemini model names are defined as constants in the AI section of `index.html`, making them easy to replace when required.

The application also includes:

* API retry handling
* Short back-off between attempts
* Fallback model support

> **Privacy:** The Gemini API key is stored only in the user's browser and is sent to Google's Gemini API when an AI feature is used. The key is not stored in this repository.

---

# 🛠️ Tech Stack

| Technology        | Purpose                                |
| ----------------- | -------------------------------------- |
| HTML              | Application structure                  |
| CSS               | Custom styling and animations          |
| JavaScript        | Application logic and state management |
| Tailwind CSS      | UI styling                             |
| Lucide Icons      | Interface icons                        |
| Google Gemini API | AI task organization and motivation    |
| localStorage      | Client-side data persistence           |
| GitHub Pages      | Deployment                             |

---

# 🏗️ Architecture

AI & Data Quest is intentionally built as a **single-file static web application**.

```text
                    ┌──────────────────┐
                    │     Browser      │
                    │                  │
                    │   index.html     │
                    └────────┬─────────┘
                             │
             ┌───────────────┼───────────────┐
             │               │               │
             ▼               ▼               ▼
       Task Manager      localStorage    Gemini API
             │               │               │
             ▼               ▼               ▼
        Daily Tasks      User Data       AI Tasks
             │
             ▼
      ┌──────────────┐
      │ Productivity │
      │   Analytics  │
      └──────┬───────┘
             │
       ┌─────┴─────┐
       ▼           ▼
    Streak      Heatmap
```

There is no server-side database or backend dependency.

---

# 🚀 Getting Started

## Run Locally

Clone the repository:

```bash
git clone https://github.com/ramya63822/ai-quest-todo.git
```

Navigate into the project:

```bash
cd ai-quest-todo
```

Then open:

```text
index.html
```

in your browser.

That's it.

No:

* `npm install`
* build process
* backend server
* database

is required.

---

# 🔑 Enable AI Features

The core productivity features work without an API key.

To enable the AI features:

### 1. Get a Gemini API Key

Create a key through Google AI Studio.

### 2. Open AI & Data Quest

Click the **🔑 API key icon** in the application header.

### 3. Add Your Key

Paste your Gemini API key and save it.

### 4. Use AI Features

Enter a brain dump and select:

**Organize Thoughts**

The AI-generated tasks will automatically be added to your checklist.

---

# 🌐 Deploy Your Own Copy

Because the application is a static HTML project, it can be deployed directly using GitHub Pages.

### Step 1 — Fork the Repository

Fork this repository to your GitHub account.

### Step 2 — Open Repository Settings

Go to:

```text
Settings → Pages
```

### Step 3 — Configure Deployment

Under **Build and deployment**:

```text
Source: Deploy from a branch
Branch: main
Folder: / (root)
```

### Step 4 — Save

GitHub Pages will deploy the application.

Your URL will look like:

```text
https://<your-username>.github.io/<repository-name>/
```

---

# 📁 Project Structure

```text
ai-quest-todo/
│
├── index.html       # Complete application
└── README.md        # Project documentation
```

The application intentionally uses a single HTML file to keep deployment and maintenance simple.

---

# 🔐 Privacy & Security

AI & Data Quest follows a **local-first architecture**.

### Stored locally

The application stores user-specific information in the browser's:

```text
localStorage
```

This includes application state such as tasks, preferences, and productivity history.

### No account required

There is no:

* User registration
* Login system
* Backend database
* Server-side user profile

### Gemini API

When an AI feature is used, the relevant user input is sent directly from the browser to Google's Gemini API.

The API key is not included in the GitHub repository.

> **Important:** Because the API key is entered and stored in the browser, this project is intended primarily as a personal/client-side application. For a production application serving many users, API requests should generally be routed through a secure backend rather than exposing API credentials in the client.

---

# 💡 Why I Built It

Most productivity applications kept adding features I didn't need.

I wanted something that answered a much simpler question:

> **"What do I actually need to get done today?"**

So I built a lightweight productivity system around three ideas:

```text
Capture → Organize → Stay Consistent
```

The AI handles the messy thinking.

The task list handles execution.

The heatmap and streak help visualize consistency.

---

# 🚧 Future Improvements

Potential improvements include:

* [ ] Drag-and-drop task ordering
* [ ] Task categories and tags
* [ ] Priority levels
* [ ] Due dates
* [ ] Calendar integration
* [ ] Export/import productivity data
* [ ] More AI-powered productivity features
* [ ] PWA / offline installation support
* [ ] Improved mobile experience
* [ ] Backend-based secure API proxy for production deployment

---

# 🤝 Contributing

This is primarily a personal project, but suggestions and contributions are welcome.

To contribute:

```bash
git clone https://github.com/ramya63822/ai-quest-todo.git
cd ai-quest-todo
```

Create a branch:

```bash
git checkout -b feature/your-feature
```

Make your changes, commit them, and open a pull request.

---

# 📄 License

This project is licensed under the **MIT License**.

You are free to use, modify, and distribute the project according to the license terms.

---

# 👩‍💻 Built By

**Ramyaa**

AI & Data Science Student

[GitHub](https://github.com/ramya63822)

---

⭐ If you find the project useful, consider giving the repository a star.
