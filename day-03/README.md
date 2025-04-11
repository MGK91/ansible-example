```markdown
# 🔐 Secure MySQL Setup & Variable Precedence with Ansible

This repository contains two mini-projects:
1. **vault-example** – Secure MySQL user/database setup using Ansible Vault
2. **ansible-var-precedence** – Demonstration of Ansible variable precedence

---

## 📁 Directory Structure

```
.
├── vault-example/
│   ├── inventory.ini
│   ├── vault_vars.yaml               # Encrypted secrets (via Ansible Vault)
│   ├── mysql_playbook.yaml           # Playbook to create MySQL DB & user
│   ├── mysql_playbook.yaml-bkp       # Backup copy
│   ├── ansible.cfg                   # Ansible config (optional socket path)
│   ├── my.cf.j2                      # Template for MySQL config
│   ├── group_vars/
│   └── templates/
│       └── my.cf.j2                  # MySQL configuration template
│
└── ansible-var-precedence/
    ├── inventory.ini
    ├── var-precendence-example.yaml  # Test playbook to show variable precedence
    ├── group_vars/
    └── host_vars/
```

---

## 🔐 Ansible Vault – Secrets Management

### Encrypt variable file:
```bash
ansible-vault encrypt vault_vars.yaml
```

Example contents before encryption:

```yaml
mysql_root_password: "Supersecret"
mysql_user: "devuser"
mysql_password: "devpass"
mysql_database: "mydb"
```

### Edit encrypted file:
```bash
ansible-vault edit vault_vars.yaml
```

---

## 🚀 Run Playbook with Vault

Prompt for vault password:
```bash
ansible-playbook mysql_playbook.yaml --extra-vars "@vault_vars.yaml" --ask-vault-pass
```

Use saved vault password file:
```bash
ansible-playbook mysql_playbook.yaml --extra-vars "@vault_vars.yaml"
```

---

## 📊 Ansible Variable Precedence

ansible-playbook -i inventory.ini var-precendence-example.yaml -e "extra_vars=extra_value"

---

## ✅ Tips & Troubleshooting

- If you face `Access denied for user 'root'@'localhost'`, verify that:
  - MySQL root access is set up
  - Unix socket path is correct
  - You're using correct auth method (password vs socket)
- Temporarily **comment out root password setup** task if it fails due to existing user auth method
- Use `ignore_errors: true` on first root password task if you're unsure

---

## 🛠️ Run MySQL Setup Step-by-Step

```bash
cd vault-example/
ansible-playbook mysql_playbook.yaml --extra-vars "@vault_vars.yaml" --ask-vault-pass
```

---

## 📂 Next Steps

- Add handlers to restart MySQL if config changes
- Include conditional checks so setup runs only once
- Add Idempotent role-based structure for reusability

---

## 🧾 Author & Credits

- Built for internal learning/testing on EC2 with MySQL & Ansible
- Vault and precedence scenarios for upskilling in DevSecOps

---
```
