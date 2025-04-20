# 🔧 Ansible Setup on Windows using WSL – Step-by-Step

Hey there! 👋  
If you're trying to get Ansible running on your Windows machine, and you're new to this – don't worry! Follow along and you'll have it up in no time.

---

## 🧱 Prerequisites

Before we begin, make sure:
- You're using Windows 10 or 11.
- You have internet access (obviously 😅).
- You've installed WSL (Windows Subsystem for Linux).
- You're comfortable using the terminal or willing to get comfortable 😎

---

### 🔷 Step 1: Install WSL (If not already done)

Open PowerShell as **Administrator** and run:

```powershell
wsl --install


To see available Linux distributions:
wsl --list --online

Now install Ubuntu:
wsl --install -d Ubuntu

🔁 Once done, reboot your system if needed.


### 🔁 Step 2: Update your Ubuntu WSL instance 

Open Ubuntu terminal (from Start menu or Windows Terminal), and run:
sudo apt update && sudo apt upgrade -y


### 🔷🛠️ Step 3: Install Ansible

Now let's install Ansible:

sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible -y

# You can verify the installation:
ansible --version
🎉 Done! Ansible is now installed inside WSL and ready to use.


### 🔷🧪 Bonus: Run a test command

Try this to ping localhost using Ansible:
ansible localhost -m ping --connection=local

If it returns pong, you’re golden 🥳



**💡 Tips**
If WSL is giving errors, try wsl --set-default-version 2 and reinstall Ubuntu.

Always install Ansible inside WSL, not on Windows directly.
