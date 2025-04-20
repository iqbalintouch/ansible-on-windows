### ⚙️ Setup & Installation Commands
These are the exact commands you used (or can use) to get Ansible up and running inside WSL:

# 1. Install WSL and Ubuntu (from PowerShell)
wsl --install
wsl --list --online
wsl --install -d Ubuntu

# 2. Update your Ubuntu packages
sudo apt update
sudo apt upgrade -y

# 3. (Optional) Install via APT repository
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible -y

#    — or —

# 3′. Install via Python virtual‑env
sudo apt install python3-venv -y
python3 -m venv ~/ansible-env
source ~/ansible-env/bin/activate
pip install ansible

# 4. Verify installation
ansible --version



### 🚀 Common Ansible Usage Commands

# 1. Ping all hosts in inventory
ansible all -m ping

# 2. Run a shell/command module ad‑hoc
ansible all -m shell -a "uptime"

# 3. Run your playbook
ansible-playbook playbook.yml

# 4. Dry‑run a playbook (check what would happen)
ansible-playbook playbook.yml --check

# 5. Syntax‑check your playbook
ansible-playbook playbook.yml --syntax-check

# 6. Specify a custom inventory
ansible-playbook -i inventory.ini playbook.yml

# 7. Inspect your inventory
ansible-inventory --list -y

# 8. Get module documentation
ansible-doc <module-name>
# e.g. ansible-doc copy

# 9. Manage roles & collections
ansible-galaxy install geerlingguy.nginx
ansible-galaxy collection list

# 10. Vault encrypt/decrypt
ansible-vault encrypt secrets.yml
ansible-vault decrypt secrets.yml

# 11. View full config
ansible-config dump --only-changed
