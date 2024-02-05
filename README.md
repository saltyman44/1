# Setup
``` bash
cd ~
pip install --upgrade pip
git clone https://github.com/tripleseven190504/change-face.git
pip install -r ~/change-face/requirements.txt
pip install fastapi kaleido python-multipart uvicorn
pip install --force-reinstall lida gcsfs google-colab huggingface-hub imageio tensorflow tensorflow-probability torchdata torchtext yfinance
wget https://huggingface.co/ezioruan/inswapper_128.onnx/resolve/main/inswapper_128.onnx -O inswapper_128.onnx
mkdir ~/change-face/models
mv inswapper_128.onnx ~/change-face/models
pip uninstall onnxruntime onnxruntime-gpu -y
pip install torch torchvision torchaudio --force-reinstall --index-url https://download.pytorch.org/whl/cu118
pip install onnxruntime-gpu
```
# Run
``` bash
cd ~/change-face
python run.py -s ~/face.jpeg -t ~/video.mp4 -o ~/new_video.mp4 --frame-processor face_swapper
```
