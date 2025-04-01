# VLLM Environment Setup Guide  

This guide will help you set up the VLLM environment with Python 3.10, CUDA 11.8, PyTorch, and xFormers.  

## 🚀 Prerequisites  

- **Conda** installed (for environment management)  
- **Python 3.10** (managed via Conda)  
- **CUDA 11.8** compatible GPU (for optimal performance)  

---

## ⚡ Step-by-Step Installation  

### 1️⃣ Create and Activate Conda Environment  

```bash
conda create -n vllm python=3.10
conda activate vllm
```
This creates a Conda environment named vllm with Python 3.10.


### 2️⃣ Set Environment Variables

```bash
export VLLM_VERSION=0.4.0
export PYTHON_VERSION=310
```
  - **VLLM_VERSION**: Specifies the version of VLLM to install.

  - **PYTHON_VERSION**: Ensures compatibility with Python 3.10.

### 3️⃣ Install VLLM
```bash
pip install https://github.com/vllm-project/vllm/releases/download/v${VLLM_VERSION}/vllm-${VLLM_VERSION}+cu118-cp${PYTHON_VERSION}-cp${PYTHON_VERSION}-manylinux1_x86_64.whl
```

This installs VLLM version 0.4.0 with CUDA 11.8 support.

### 4️⃣ Reinstall PyTorch with CUDA 11.8

```bash

pip uninstall torch -y
pip install torch==2.1.2+cu118 --index-url https://download.pytorch.org/whl/cu118
```

Ensures PyTorch is compatible with CUDA 11.8.

### 5️⃣ Reinstall xFormers with CUDA 11.8
```bash
pip uninstall xformers -y
pip install xformers==0.0.23.post1+cu118 --index-url https://download.pytorch.org/whl/cu118
```

This installs the xFormers library optimized for CUDA 11.8.

### ✅ Verify Installation

After installation, verify the setup with:
```bash
python -c "import torch; print(torch.__version__)"
python -c "import vllm; print(vllm.__version__)"
python -c "import xformers; print(xformers.__version__)"
```


### 📝 Notes

  - If you encounter issues, ensure your GPU drivers and CUDA toolkit are up-to-date.

  - For troubleshooting, refer to the VLLM GitHub Issues.

