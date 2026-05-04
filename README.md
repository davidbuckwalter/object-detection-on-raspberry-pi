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

CSI camera module is used as default in the source code. If you're using a WebCam, modify the subprogram call in the `main.py` on `detect.py`.

If you're using a WebCam, change the subprogram call in `main.py` to:
```python
# detect(True, DISPLAY_WIDTH, DISPLAY_HEIGHT, THREAD_NUM, False)
detect(False, DISPLAY_WIDTH, DISPLAY_HEIGHT, THREAD_NUM, False)
```

```shell
$ python3 src/detect.py
```

You should see the camera feed appear on the monitor attached to your Raspberry Pi. Put some objects in front of the camera, like a coffee mug or keyboard, and you'll see boxes drawn around those that the model recognizes, including the label and score for each. It also prints the number of frames per second (FPS) at the top-left corner of the screen. As the pipeline contains some processes other than model inference, including visualizing the detection results, you can expect a higher FPS if your inference pipeline runs in headless mode without visualization.

## Speed up model inference (with Coral USB Accelerator)
If you want to significantly speed up the inference time, you can attach an
[Coral USB Accelerator](https://coral.withgoogle.com/products/accelerator)—a USB
accessory that adds the
[Edge TPU ML accelerator](https://coral.withgoogle.com/docs/edgetpu/faq/) to any
Linux-based system.

If you have a Coral USB Accelerator, you can run the sample with it enabled:

1.  First, be sure you have completed the
    [USB Accelerator setup instructions](https://coral.withgoogle.com/docs/accelerator/get-started/).

2.  Run the object detection script using the EdgeTPU TFLite model and enable
    the EdgeTPU option. Be noted that the EdgeTPU requires a specific TFLite
    model that is different from the one used above.
    Change the subprogram call in `main.py` to:

```python
# detect(False, DISPLAY_WIDTH, DISPLAY_HEIGHT, THREAD_NUM, False)
detect(False, DISPLAY_WIDTH, DISPLAY_HEIGHT, THREAD_NUM, True)
```
Then run:
```shell
$ python3 src/detect.py
```

You should see significantly faster inference speeds.
