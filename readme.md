# 💼 Personal Career Chatbot (Gradio + OpenAI + Tool Calling)

This project is a **personal career chatbot** that represents you professionally using OpenAI’s chat completions API, Gradio for the UI, and demonstartes AI tool‑calling.

It loads your résumé, LinkedIn PDF, and a summary file to answer questions about your background, skills, and experience.

The chatbot can:

- Answer questions about your career and experience  
- Stay in character as you  
- Ask visitors for their email  
- Log unknown questions  
- Send notifications via Pushover  
- Display a clean, responsive Gradio chat interface  

---

## 🚀 Features

- **Persona‑driven responses** using your résumé, LinkedIn PDF, and summary  
- **Tool calling** for:
  - Recording user details (email, name, notes)
  - Logging unknown questions  
- **Pushover integration** for instant notifications  
- **Responsive Gradio UI** with your profile image  
- **PDF ingestion** using `pypdf`  
- **Simple, clean architecture**  

---
## 📦 Installation

### 1. Clone the repository

'''bash
git clone <your-repo-url>
cd <your-repo>
pip install -r requirements.txt



### Create a .env file
Your .env must include:

OPENAI_API_KEY=your_key_here
PUSHOVER_TOKEN=your_pushover_app_token
PUSHOVER_USER=your_pushover_user_key


🧩 Required Files in ./me Directory

Before running the chatbot, you must add your own personal files to the ./me folder:

image.jpg -   Your profile photo (displayed at the top of the chatbot)

linkedin.pdf  -  Export of your LinkedIn profile as a PDF

resume.pdf   - Your résumé/CV in PDF format

summary.txt  - A short written summary of your background

###Example files included

The repo includes example placeholders prefixed with Example_:

Example_Image.jpg

Example_LinkedIn.pdf

Example_Resume.pdf

Example_Summary.txt

Use these as a reference, then replace them with your own files (renamed to the required filenames above).

▶️ Running the Chatbot

Once your ./me directory contains the required files:

python main.py

Gradio will launch a local web UI in your browser.

🛠 How It Works

1. Persona Loading

The app loads:

summary.txt

linkedin.pdf

resume.pdf

These are injected into the system prompt so the model can answer questions about your background.

2. Tool Calling

Two tools are available:

record_user_details(email, name, notes)

record_unknown_question(question)

The model automatically calls these when appropriate.

3. Notifications

All tool calls send a message to your Pushover account.

4. Chat Loop

The app continues processing tool calls until the model returns a final answer.

🖼 UI Preview

The Gradio interface includes:

Your profile image

A title using your name

Example questions

A scrollable chat window

🧪 Example Questions

“Tell me about your background”

“What skills do you have?”

“How can I get in touch?”

🌐 Deploying to Hugging Face Spaces

You can deploy this chatbot to Hugging Face Spaces so it runs 24/7 and can be shared on:

LinkedIn

Your résumé

Your personal website

Email signatures

This makes it incredibly easy for recruiters or clients to interact with your AI‑powered career assistant.

🚀 1. Create a New Space

Go to: https://huggingface.co/spaces

Click “Create new Space”

Choose:

Space name: e.g., yourname-career-chatbot

SDK: Gradio

Visibility: Public (recommended for sharing)

Click Create Space

📁 2. Upload Your Project Files

Your repository should contain:

main.py
requirements.txt
README.md
/me/
    image.jpg
    linkedin.pdf
    resume.pdf
    summary.txt

Important

You must upload your own personal files into the me/ directory:


🔑 3. Add Your Secrets (Environment Variables)

Hugging Face Spaces supports secure secrets.

Open your Space

Go to Settings → Variables and secrets

Add:


   KEY                  Value
OPENAI_API_KEY     your OpenAI API key

PUSHOVER_TOKEN     your Pushover app token

PUSHOVER_USER      your Pushover user key

These are stored securely and not visible to users.

📦 4. Add a requirements.txt


▶️ 5. Deploy Hugging Face (Notes)


1. From the Avatar menu on the top right, choose Access Tokens. Choose "Create New Token". Give it WRITE permissions - it needs to have WRITE permissions! Keep a record of your new key. 

Two options to install 

From terminal: run gradio deploy in your app directory. 

From your browser: Drag and drop a folder containing your Gradio model and all related files

More info can be found here
https://www.gradio.app/guides/sharing-your-app#hosting-on-hf-spaces


Once all files are uploaded:

Hugging Face will automatically build and run your Space

After a minute or two, you’ll see a green Running indicator

Your chatbot will be live at:

https://huggingface.co/spaces/<your-username>/<your-space-name>

This link is permanent and public.

🔗 6. Share the Link

You can now add the link anywhere:

LinkedIn

“Chat with my AI career assistant: <your-space-url>”

Résumé

Under your contact details:AI Career Chatbot: <your-space-url>

Email signature

“Ask my AI assistant about my experience: <your-space-url>”

Portfolio website

Embed the Space directly or link to it






