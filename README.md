# 🧠 Object Detection on Raspberry Pi (Offline + Git LFS Supported)

This project contains an **object detection system for Raspberry Pi 4B**, including:
- Python code
- Pre-downloaded dependencies (APT + pip)
- Large model / package support via **Git LFS**
- Offline installation workflow

---

# ⚠️ Important Notice

This repository uses **Git LFS (Large File Storage)** for large files such as:
- `.deb` packages
- `.whl` Python wheels
- ML models
- Prebuilt dependencies

👉 You MUST install Git LFS before cloning.

---

# 🚀 1. Prerequisites

## Install Git LFS

### Ubuntu / Debian
```bash
sudo apt update
sudo apt install git-lfs -y
git lfs install
