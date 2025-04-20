# 🚀 Ansible on Windows (via WSL) — Beginner Friendly Setup Guide

This guide walks you through setting up Ansible on Windows using WSL (Windows Subsystem for Linux). It's beginner-friendly, with explanations, troubleshooting steps, and helpful tips.

---

## 🧱 Prerequisites

- A Windows 10/11 machine
- WSL installed (We’ll use Ubuntu)
- VS Code installed (optional, but recommended)
- Basic familiarity with terminal commands

---

## 🔧 Step 1: Install WSL and Ubuntu

```powershell
wsl --install
wsl --list --online
wsl --install -d Ubuntu
