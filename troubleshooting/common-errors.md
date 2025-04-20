# 🐞 Common Ansible Errors & Fixes

Facing weird issues while using Ansible?  
Don't worry, you're not alone! Here's a list of common problems and how to fix them.

---

❌ Error 1: "command not found: ansible"
What it means: Ansible isn’t installed or isn’t available in the shell’s `$PATH`.

**✅ Fix:**
```bash
sudo apt install ansible -y

After installing, verify:
ansible --version


❌ Error 2: "Permission denied" while running playbooks
What it means: You're trying to run a task that needs elevated privileges.

✅ Fix: Add become: true in your playbook/task or run:

ansible-playbook site.yml --ask-become-pass


❌ Error 3: "hosts file not found" or "No hosts matched"
What it means: Your inventory file isn’t being picked up or the host group doesn’t exist.

✅ Fix:
Ensure inventory file is passed using -i:

ansible -i inventory.ini all -m ping
Check that group names in the playbook match inventory.


❌ Error 4: "UNREACHABLE" host
What it means: The host is unreachable via SSH.

✅ Fix:
Check network connectivity:
ping <host-ip>

Try SSH manually:
ssh user@host
Ensure correct username/key is used in inventory or ansible.cfg.

❌ Error 5: "Missing sudo password"
What it means: You're trying to become root but haven't supplied a password.

✅ Fix:

Run with:
ansible-playbook site.yml --ask-become-pass
Or configure ansible_become_password in variables.


❌ Error 6: WSL: "Permission denied" or "Cannot write to folder"
What it means: You're trying to run Ansible in a Windows directory via WSL.

✅ Fix: Always run Ansible inside the WSL Linux filesystem, not inside /mnt/c/ paths.


🛠️ Tip: Use Verbose Mode for Debugging
Add -vvv for detailed logs:


ansible-playbook playbook.yml -vvv
