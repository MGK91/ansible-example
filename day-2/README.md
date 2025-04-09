# 📘 Ansible Playbook Execution Commands

This document contains various Ansible playbook execution commands used for different scenarios such as dry run, tagging, verbose logging, looping, handlers, blocks, and roles.

---

## ✅ Dry Run (`--check`)
```bash
ansible-playbook nginx.yam -i dev.ini --check
ansible-playbook nginx.yaml -i dev.ini --check
ansible-playbook nginx.yaml -i dev.ini --check
ansible-playbook nginx.yaml -i dev.ini --check
ansible-playbook fact.yaml -i dev.ini --check
ansible-playbook fact.yaml -i dev.ini --check
ansible-playbook fact.yaml -i dev.ini --check
```

---

## 📊 Facts Gathering
```bash
ansible-playbook fact.yaml -i dev.ini
```

---

## 🧪 Example Playbook
```bash
ansible-playbook example.yaml -i dev.ini
ansible-playbook example.yaml -i dev.ini
```

---

## 🖁️ Handler Execution
```bash
ansible-playbook handler.yaml -i dev.ini
```

---

## 🏷️ Tagged Execution
```bash
ansible-playbook tags.yaml -i dev.ini --tags configure
ansible-playbook tags.yaml -i dev.ini --tags start
```

---

## 🧱 Block with Error Handling
```bash
ansible-playbook block.yaml -i dev.ini
```

---

## 📋 Register Variables
```bash
ansible-playbook -vvv register.yaml -i dev.ini
ansible-playbook register.yaml -i dev.ini
```

---

## 🔂 Loop Example
```bash
ansible-playbook loop.yaml -i dev.ini
```

---

## 📦 Role-Based Playbook
```bash
ansible-playbook site.yaml -i dev.ini
```

---

> ✍️ Maintained by: [Your Name or Team]  
> 🗓️ Last updated: April 2025


