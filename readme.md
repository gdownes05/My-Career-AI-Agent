# 💼 Personal Career Chatbot (Gradio + OpenAI + Tool Calling)

A **personal career chatbot** that represents you professionally using **OpenAI Chat Completions**, **Gradio** for the UI, and **tool calling** for structured actions like logging user details and unknown questions.

It loads your **résumé**, **LinkedIn PDF**, and **summary file** to answer questions about your background, skills, and experience.

---

## ✨ What It Can Do

- Answer questions about your career and experience  
- Stay **in character** as you  
- Ask visitors for their email  
- Log unknown or unanswered questions  
- Send notifications via **Pushover**  
- Display a clean, responsive **Gradio chat interface**  

---

## 🚀 Features

- **Persona-driven responses** using your résumé, LinkedIn PDF, and summary  
- **Tool calling** for:
  - Recording user details (email, name, notes)
  - Logging unknown questions  
- **Pushover integration** for instant notifications  
- **Responsive Gradio UI** with your profile image  
- **PDF ingestion** using `pypdf`  
- **Simple, clean architecture**  

---

## 📦 Installation

### 1) Clone the repository

```bash
git clone <your-repo-url>
cd <your-repo>
pip install -r requirements.txt
```

---

## 🔐 Environment Variables

### 2) Create a `.env` file

Your `.env` must include:

```env
OPENAI_API_KEY=your_key_here
PUSHOVER_TOKEN=your_pushover_app_token
PUSHOVER_USER=your_pushover_user_key
```

---

## 🧩 Required Files in `./me`

Before running the chatbot, add your personal files into the `./me` directory:

| File | Description |
|------|-------------|
| `image.jpg` | Your profile photo (displayed at the top of the chatbot) |
| `linkedin.pdf` | Export of your LinkedIn profile as a PDF |
| `resume.pdf` | Your résumé/CV in PDF format |
| `summary.txt` | A short written summary of your background |

### Example placeholder files

The repo includes example placeholders prefixed with `Example_`:

- `Example_Image.jpg`
- `Example_LinkedIn.pdf`
- `Example_Resume.pdf`
- `Example_Summary.txt`

Use these as a reference, then replace them with your own files (renamed to the required filenames above).

---

## ▶️ Running the Chatbot

Once your `./me` directory contains the required files:

```bash
python main.py
```

Gradio will launch a local web UI in your browser.

---

## 🛠 How It Works

### 1) Persona Loading

The app loads:

- `summary.txt`
- `linkedin.pdf`
- `resume.pdf`

These are injected into the **system prompt** so the model can answer questions about your background.

### 2) Tool Calling

Two tools are available:

- `record_user_details(email, name, notes)`
- `record_unknown_question(question)`

The model automatically calls these when appropriate.

### 3) Notifications

All tool calls send a message to your **Pushover** account.

### 4) Chat Loop

The app continues processing tool calls until the model returns a final answer.

---

## 🖼 UI Preview

The Gradio interface includes:

- Your profile image  
- A title using your name  
- Example questions  
- A scrollable chat window  

---

## 🧪 Example Questions

Try asking:

- “Tell me about your background”
- “What skills do you have?”
- “How can I get in touch?”

---

## 🌐 Deploying to Hugging Face Spaces

You can deploy this chatbot to **Hugging Face Spaces** so it runs 24/7 and can be shared on:

- LinkedIn
- Your résumé
- Your personal website
- Email signatures

This makes it easy for recruiters or clients to interact with your AI-powered career assistant.

---

### 🚀 1) Create a New Space

1. Go to: `https://huggingface.co/spaces`
2. Click **Create new Space**
3. Choose:
   - **Space name:** `yourname-career-chatbot`
   - **SDK:** Gradio
   - **Visibility:** Public (recommended for sharing)
4. Click **Create Space**

---

### 📁 2) Upload Your Project Files

Your repository should contain:

```text
main.py
requirements.txt
README.md
/me/
  image.jpg
  linkedin.pdf
  resume.pdf
  summary.txt
```

> ✅ Important: You must upload your own personal files into the `me/` directory.

---

### 🔑 3) Add Your Secrets (Environment Variables)

Hugging Face Spaces supports secure secrets.

1. Open your Space  
2. Go to **Settings → Variables and secrets**  
3. Add:

| Key | Value |
|-----|-------|
| `OPENAI_API_KEY` | your OpenAI API key |
| `PUSHOVER_TOKEN` | your Pushover app token |
| `PUSHOVER_USER` | your Pushover user key |

These are stored securely and not visible to users.

---

### 📦 4) Add a `requirements.txt`

Make sure your Space includes a `requirements.txt` so Hugging Face can install dependencies.

---

### ▶️ 5) Deploy to Hugging Face (Notes)

To deploy using an access token:

1. From the avatar menu (top right), choose **Access Tokens**
2. Click **Create New Token**
3. Give it **WRITE permissions** (important!)
4. Keep a record of your new token

**Two options to deploy:**

✅ **Option A: Deploy from terminal**
```bash
gradio deploy
```

✅ **Option B: Deploy via browser**
- Drag and drop a folder containing your Gradio app and all related files

More info:
`https://www.gradio.app/guides/sharing-your-app#hosting-on-hf-spaces`

---

### ✅ Once Deployed

After files are uploaded:

- Hugging Face will automatically build and run your Space  
- After a minute or two, you’ll see a green **Running** indicator  
- Your chatbot will be live at:

```text
https://huggingface.co/spaces/<your-username>/<your-space-name>
```

This link is permanent and public.

---

## 🔗 Sharing Your Chatbot

You can now share the link anywhere:

- **LinkedIn:** “Chat with my AI career assistant: <your-space-url>”
- **Résumé:** “AI Career Chatbot: <your-space-url>”
- **Email signature:** “Ask my AI assistant about my experience: <your-space-url>”
- **Portfolio website:** Embed the Space directly or link to it

---
