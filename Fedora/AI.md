# ComfyUI:

```bash

mkdir ComfyUI

git clone https://github.com/comfyanonymous/ComfyUI.git --branch v0.3.40

python -m venv comfyui

source comfyui/bin/activate

sudo dnf install cmake

pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/rocm6.3

pip install -r requirements.txt

python main.py
``
