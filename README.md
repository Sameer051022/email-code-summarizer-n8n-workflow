# 📧 Email Code Summarizer — AI-Powered n8n Workflow

[![n8n](https://img.shields.io/badge/Powered%20by-n8n-orange?logo=n8n)](https://n8n.io)
[![OpenAI](https://img.shields.io/badge/AI-OpenAI-412991?logo=openai)](https://platform.openai.com)
[![Gmail](https://img.shields.io/badge/Email-Gmail-red?logo=gmail)](https://mail.google.com)
[![License](https://img.shields.io/badge/License-TBD-lightgrey.svg)](#license)

> **An automated n8n workflow that watches your Gmail inbox for code, summarizes it and adds comments using OpenAI, and emails the finished report straight back to you.**

---

## ✨ Features

| Capability | Description |
|---|---|
| 📥 **Email Trigger** | Automatically detects incoming emails containing code |
| 🧠 **Code Summary** | Uses OpenAI to generate a clear summary of what the code does |
| 💬 **Auto Comments** | Generates line-by-line comments to document the code |
| 🔀 **Parallel Processing** | Runs summary and comment generation simultaneously for speed |
| 📤 **Auto Reply** | Emails the combined, formatted result back automatically |

---

## 🏗️ Tech Stack

- **Workflow Automation**: [n8n](https://n8n.io) — self-hosted workflow engine
- **Email**: Gmail — trigger and delivery
- **AI Backend**: [OpenAI](https://platform.openai.com) — code summarization and comment generation

---

## 🔧 Workflow Breakdown

1. **Gmail Trigger** — Watches the inbox and fires when a new email containing code arrives
2. **If Node** — Validates the incoming email and content before processing
3. **Parallel AI Processing** — A Code Summary chain and a Comments Addition chain run simultaneously via OpenAI
4. **Merge** — Combines the two parallel outputs into a single data stream
5. **Aggregate** — Consolidates the merged items into one unified payload
6. **Edit Fields** — Concatenates and formats the final text for readability
7. **Basic LLM Chain** — Performs a final pass over the combined content to polish it
8. **Send Email** — Delivers the finished summary and commented code back via Gmail

---

## 🚀 Getting Started

### Prerequisites

- A running n8n instance (self-hosted or cloud)
- Gmail account connected via OAuth2 credentials in n8n
- OpenAI API key configured as a credential in n8n

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Sameer051022/email-code-summarizer-n8n-workflow.git
cd email-code-summarizer-n8n-workflow
```

### Import the Workflow

1. Open your n8n instance
2. Go to **Workflows → Import from File**
3. Select the workflow JSON from this repository (to be added)
4. Configure the Gmail and OpenAI credentials on their respective nodes

### Run It

1. Activate the workflow in n8n
2. Send a test email containing a code snippet to the connected Gmail account
3. Check your inbox for the automated summary and comments reply

---

## 📁 Project Structure

```
email-code-summarizer-n8n-workflow/
├── workflow.json   # n8n workflow export (to be added)
└── README.md       # This file
```

---

## 📌 Project Status

This repository currently contains project documentation only. The workflow export file and any supporting assets will be added soon.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

A license has not been chosen for this project yet. It will be added once the workflow files are published.

---

## 👤 Author

**Sameer Faisal**

- GitHub: [@Sameer051022](https://github.com/Sameer051022)

---

<p align="center">Powered by n8n · Built with ❤️ using OpenAI</p>
