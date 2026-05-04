# 📦 Downloading Git LFS Files on Windows

This repository uses **Git Large File Storage (Git LFS)** for storing large files such as:
- `.deb` packages
- `.whl` Python wheels
- ML models
- datasets and binaries

⚠️ IMPORTANT: If you do NOT use Git LFS correctly, you will only download *pointer files*, not real data.

---

# How to download?

## Step 1 — Download Git LFS installer and Install it

👉 https://git-lfs.com/

Run the installer and complete setup.

---

## Step 2 — Enable Git LFS and Clone this repository

Open **Command Prompt** or **Git Bash**:

```
git lfs install
git clone https://github.com/davidbuckwalter/object-detection-on-raspberry-pi
