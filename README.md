<p align="center">
  <img src="https://registry.npmmirror.com/@lobehub/icons-static-png/latest/files/dark/ollama.png" width="128" />
</p>
<h1 align="center">Ollama on Google Colab</h1>

[![Repo Size](https://img.shields.io/github/repo-size/userNOTfound-bot/Ollama-Google-Colab)](https://github.com/userNOTfound-bot/Ollama-Google-Colab)
[![License](https://img.shields.io/github/license/userNOTfound-bot/Ollama-Google-Colab)](https://github.com/userNOTfound-bot/Ollama-Google-Colab/blob/main/LICENSE)

> A lightweight Colab-based wrapper for Ollama using cloudflared tunnels, allowing free users to create temporary public links.

## 🚀 Quick Start & Usage

1.  Click the "Open in Colab" badge below to open the notebook.

     [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/userNOTfound-bot/Ollama_using_Google-Colab/blob/main/ollama_using_Google_Colab.ipynb)

2.  Change the Runtime to T4 GPU (⚠️Warning: Google-Colab only gives you GPU usage upto 12-hours in a day).
3.  Run the notebook cells to install dependencies and launch the tunnel.
4.  Then it will provides you an cloudflared temporary public tunnel (temporary means it will generate new URL everytime when you run this NOTEBOOK, & it will work until you 'Delete the runtime usage')
<p align="center">
  <img width="674" height="144" alt="Screenshot 2025-09-26 221503" src="https://github.com/user-attachments/assets/dd66cca5-74fb-4a63-a4d4-f980469b9042" />
  <br>
  <i>Example: Cloudflare Tunnel successfully created</i>
</p>

5.  Now you can use this public link in anywhere(Open Web-UI, terminal etc.) instead of Ollama local server (http://127.0.0.1:11434).
6.  How to set that public link in terminal for that terminal session (means the particular tab in terminal you run this, if you close that you need to terminal process again), Heres how you can do (⚠️You must had Ollama installed in you OS (https://ollama.com/download)):
    *   **Windows:**
       *   **PowerShell:**
            ```bash
            $env:OLLAMA_HOST="<you_provided_cloudflared_public>"
            ```
       *   **CMD:**
            ```bash
            set OLLAMA_HOST=<you_provided_cloudflared_public>
            ```
            
  *   **Linux/MacOS(Bash/Zsh):**
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
2.  **Set Up a Web Server:** It then runs the Ollama server.
3.  **Create a Public Tunnel:** It uses `cloudflared` to create a public URL that tunnels to the Ollama server running on the Colab instance.

This allows you to access the Ollama API from your local machine without having to install it locally.

## ✨ Features

*   **Free to Use:** You can use T4-GPU 12/24 hours, and with CPU unlimited but it feels way slower.
*   **Forget about less-storage in PC/Laptop:** No need to install LLM-models on local setup.
*   **Publicly Accessible:** Get a temporary public URL to share or use in your applications.
*   **Easy to Use:** Just open the notebook and run the cells.

## 📖 Notebook Details

The `ollama_using_Google_Colab.ipynb` notebook contains the following key steps:

*   **Installation of Ollama:**
    ```bash
    !curl https://ollama.ai/install.sh | sh
    ```
*   **Installation of `cloudflared`:**
    ```bash
    !wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb && dpkg -i cloudflared-linux-amd64.deb
    ```
*   **Running the Server and Tunnel:**
    ```python
    import os
    os.environ['OLLAMA_HOST'] = '0.0.0.0'
    # ... (rest of the python script)
    ```

---

Enjoy using Ollama on Colab! If you have any questions or feedback, please open an issue.
