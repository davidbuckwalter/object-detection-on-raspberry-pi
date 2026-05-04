# How to download?

This repository uses **Git Large File Storage (Git LFS)** for storing large files such as:
- `.deb` packages
- `.whl` Python wheels
- ML models
- datasets and binaries

⚠️ IMPORTANT: If you do NOT use Git LFS correctly, you will only download *pointer files*, not real data.

## Step 1 — Download Git LFS installer and Install it

👉 https://git-lfs.com/

Run the installer and complete setup.


## Step 2 — Enable Git LFS and Clone this repository

Open **Command Prompt** or **Git Bash**:

```
git lfs install

git clone https://github.com/davidbuckwalter/object-detection-on-raspberry-pi
```

# How to use this project?

## Step 1 - Install all packages
```
cd packages/apt
sudo apt install ./*.deb

cd ..
cd ..
python3 -m venv .venv
source .venv/bin/activate
pip install --no-index --find-links=packages/ -r requirements.txt
```

## Step 2 - Run detect.py file

```
python3 src/detect.py
```
