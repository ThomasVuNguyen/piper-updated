``` sh
cd piper/src/python
python3 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install --upgrade wheel setuptools
pip install cython
sudo apt install espeak-ng libespeak-ng-dev
pip install piper-tts onnx
pip install librosa numpy onnxruntime pytorch-lightning torch 
# pip install git+https://github.com/rhasspy/piper-phonemize.git
```

``` sh
python3 -m piper_train.export_onnx_streaming ljspeech-2000.ckpt output/
```

``` sh
git clone https://github.com/rockchip-linux/rknn-toolkit2
cd rknn-toolkit2/rknn-toolkit2/packages
pip install rknn_toolkit2-1.6.0+81f21f4d-cp310-cp310-linux_x86_64.whl
cd ../../..
git clone https://github.com/Luna-Inference/luna1-voice.git
cd luna1-voice
pip uninstall numpy
pip install numpy==1.24.3
python tools/decoder2rknn.py /path/to/model/decoder.onnx /path/to/model/decoder.rknn

```