<p align="center">
  <img src="https://registry.npmmirror.com/@lobehub/icons-static-png/latest/files/dark/ollama.png" width="128" />
</p>
<h1 align="center">Ollama on Google Colab</h1>

[![Repo Size](https://img.shields.io/github/repo-size/userNOTfound-bot/Ollama-Google-Colab)](https://github.com/userNOTfound-bot/Ollama-Google-Colab)
[![License](https://img.shields.io/github/license/userNOTfound-bot/Ollama-Google-Colab)](https://github.com/userNOTfound-bot/Ollama-Google-Colab/blob/main/LICENSE)

> A lightweight Colab-based wrapper for Ollama using cloudflared tunnels, allowing free users to create temporary public links.

## 🚀 Quick Start & Usage

1.  Click the "Open in Colab" badge below to open the notebook.

     [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/userNOTfound-bot/Ollama-Google-Colab/blob/main/Ollama_Google_Colab.ipynb)

2.  Change the runtime to **T4 GPU**. (⚠️ **Warning:** Google Colab provides T4 GPU access for up to 12 hours a day).
3.  Run the notebook cells to install dependencies and launch the tunnel.
4.  A temporary public URL will be generated via `cloudflared`. This link will remain active as long as the Colab notebook is running and a new URL will be generated each time you restart the notebook.
<p align="center">
  <img width="674" height="144" alt="Screenshot 2025-09-26 221503" src="https://github.com/user-attachments/assets/dd66cca5-74fb-4a63-a4d4-f980469b9042" />
  <br>
  <i>Example: Cloudflare Tunnel successfully created</i>
</p>

5.  You can use this public link with any application that integrates with Ollama, such as Open Web-UI or your terminal, as a replacement for the default local server address (`http://127.0.0.1:11434`).
6.  To use the public link in your terminal for the current session, follow these steps (**Note:** You must have Ollama installed on your local machine: https://ollama.com/download):
   *   **Windows:**
       *   **PowerShell:**
            ```bash
            $env:OLLAMA_HOST="<you_provided_cloudflared_public>"
            ```
       *   **CMD:**
            ```bash
            set OLLAMA_HOST=<you_provided_cloudflared_public>
            ```
            
  *   **Linux/MacOS (Bash/Zsh):**
      ```bash
      export OLLAMA_HOST="<you_provided_cloudflared_public>"
      ```
      
*   **Example - Windows(Powershell)👇**
    <video src="https://github.com/user-attachments/assets/db3c627e-db9c-4784-ac0a-0a25899e323d" controls="true" width="100%">
    Your browser does not support the video tag.
    </video>

## 🤔 How It Works

This project uses a Google Colab notebook to:

1.  **Install Ollama:** The notebook first installs Ollama on the Colab instance.
2.  **Run the Ollama Server:** It then starts the Ollama server.
3.  **Create a Public Tunnel:** It uses `cloudflared` to create a public URL that tunnels to the Ollama server running on the Colab instance.

This allows you to access the Ollama API from your local machine without needing to install the models locally.

## ✨ Features

*   **Free to Use:** Access Google Colab's T4 GPUs for free, subject to usage limits, or use CPU resources without time restrictions (though with slower performance).
*   **No Local Storage Needed:** Run large language models without using storage on your local machine.
*   **Publicly Accessible:** Get a temporary public URL to share or use in your applications.
*   **Easy to Use:** Just open the notebook and run the cells.

---

Enjoy using Ollama on Colab! If you have any questions or feedback, please open an issue.
