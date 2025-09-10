--- 
tags: [#ops]
created: 10-09-2025
--- 
## 🔹 Definition / Formula
- : Comman Line Inference 

  
## 🔹 Explanation (in my words)
A **CLI** is a text-based interface used to interact with a computer's operating system or an application. Instead of using a mouse to click on icons and menus, a user types commands directly into a terminal or console to perform tasks.
## 🔹 Components
- **Command**: The specific instruction to be executed (e.g., `git`, `docker`, `kubectl`).
    
- **Options/Flags**: Modifiers that change the behavior of the command (e.g., `-v` for verbose, `--help` to show options).
    
- **Arguments**: The input provided to the command, such as a filename or a value (e.g., `my_app.py`, `v1.2.0`).

## 🔹 Context 
- **DevOps**: CLIs are fundamental in DevOps for **automation** and **infrastructure management**. They are used to control tools for version control (`git`), containerization (`docker`), orchestration (`kubectl`), and cloud services (`aws cli`, `gcloud`). They allow for tasks to be scripted, ensuring reproducibility and consistency across environments

## 🔹 Related
-[[Hugging Face]] - [[Git]]-  [[Terminal]] - [[GUI (Graphical User Interface)]]

## 🔹 Examples / Applications
- Here are two examples of using CLIs in a DevOps context, specifically with Git and Hugging Face.

### Example 1: Git CLI for SSH and Token Creation

1. **Generate an SSH key pair**: Use the `ssh-keygen` command in your terminal. This command is a standard part of most operating systems and is essential for secure, password-less authentication with Git servers like GitHub.
    
    Bash
    
    ```
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```
    
2. **Add the public key to your GitHub account**: Copy the contents of the `id_ed25519.pub` file and paste it into the "SSH and GPG keys" section of your GitHub settings.
    
3. **Clone a repository using SSH**: Use the `git clone` command with the SSH URL, which is more secure and doesn't require entering credentials for every operation.
    
    Bash
    
    ```
    git clone git@github.com:your-username/your-repo.git
    ```
    
    This process is more efficient and secure than using personal access tokens for every interaction.
    

### Example 2: Hugging Face CLI for Token Creation and Login

1. **Generate an access token**: Go to your Hugging Face account settings, navigate to "Access Tokens," and create a new token with appropriate permissions.
    
2. **Log in to Hugging Face from the CLI**: Use the `huggingface-cli login` command and paste the token you just created. This securely stores your credentials on your machine.
    
    Bash
    
    ```
    huggingface-cli login
    # Paste your token when prompted
    ```

## 🔹 Source 
- Online docs 