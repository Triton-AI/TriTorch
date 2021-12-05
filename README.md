# TriTorch - Jetracer build
**Summary:** TriTorch is a modified version of the [Jetracer robot](https://github.com/NVIDIA-AI-IOT/jetracer). Go to the `develop` branch to try out new features. 

![f](TriTorch_logo.png)

---


Installation & Training Process
===

### **Step 0** - Flash your 64GB SD card with the TriTorch image:

[TriTorch1p0.img](https://drive.google.com/drive/folders/1iHAnvxUPwver9WBQoNlCFdPhGg1cJ8wM?usp=sharing)

---

### **Step 1** - Connect a monitor, keyboard and mouse to your Jetson Nano and configure your WIFI settings.
- right-click and open a terminal.
- `ifconfig`
- Check your IP address and take note. 

---

### **Step 2** - Connect to your Jetson Nano with you local machine via Jupyterlabs:
- Type in the IP address in the local machine webrowser. 
- `http://#.#.#.#:8888/`

---

### **Step 3** - Navigate to the working notebooks:

- `TriTorch/notebooks/`
- Start with `interactive_regression.ipynb`.
- Convert model with `torch2trt.ipynb`.
- Test model with `TriTorch_run.ipynb`.

### **FINISHED**
---
---
---


### Below are **extra steps** to improve data quality, but are not required. 

### **Step 4** - Alternative data collecting:

- Try out `collect_images.ipynb` and drive the car manually while it takes pictures. This will require post processing on your local machine with the `postprocess_images.py` file. 
- You can transfer these processed images back to your Jetson Nano to finish training or transfer to Google Colab. 

---

### **Step 5** - Google Colab training:

- Install [Google Colaboratory](https://colab.research.google.com/notebooks/intro.ipynb) for your **Google drive**.
- Copy `TriTorch_Colab` folder to your Google Drive if you wish to utilize Google Colab GPUs.
- Follow `TriTorch_regression.ipynb` to complete GPU training. 
- Transfer model to Jetson Nano to convert to trt and test model. 

### **FINISHED**
---
---
---

**Jetracer Terminology:**

**Jetracer** is a [NIVIDA open source](https://github.com/abritten/jetracer) road following algorithm. It is software that can be used on any kind of car using a Jetson Nano GPU.

**Jetsim** is a folder containing the Jetracer algorithm but can can interface with the Donkeycar simulator. Triton AI has developed this desktop computer version to take it off the Jetson Nano.

**"jetsim" Environment** is the Jetracer environment for a desktop computer. Triton AI is developing this now so that Jetsim can run in this desktop virtual environments. This should be built using conda. 

**jetsim-local** is the Jetsim local folder and needed files for a desktop computer. This will connect with your local Donkeycar simulator for driving manually and collecting data only.  

**jetsim-google-colab** is the Jetsim folder and needed files for a Google Drive setup. This will allow you to train on Colab GPU's and connect you to the virtual race track to test and race your model.  

**Jetcard** is a [flashed image](https://github.com/NVIDIA-AI-IOT/jetcard) with the Jetracer environment. This is ONLY used for SD cards for the Jetson Nanos to run Jetracer.

**Jetson Nano** is a small developer kit CPU with CUDA GPU programming capabilites. It typically runs Ubuntu 18.04 on arm64. Most applications do not work on arm64.

**gym-donkeycar** is the [OpenAI gym environment](https://github.com/tawnkramer/gym-donkeycar) to interface a AI framewrok with the Donkeycar similator. 

**Donkeycar simulator** like a video game, simulates a 3D car that can take control inputs and return images. This Jetsim will work with the latest version [Race Edition 21.04.15](https://github.com/tawnkramer/gym-donkeycar/releases/tag/v21.04.15)

---
