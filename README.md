
<div align="center">

<h1>Retrieval-based Voice Conversion WebUI</h1>
A simple and easy-to-use voice conversion framework based on VITS<br><br>

[![madewithlove](https://img.shields.io/badge/made_with-%E2%9D%A4-red?style=for-the-badge&labelColor=orange)](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI)

<img src="https://counter.seku.su/cmoe?name=rvc&theme=r34" /><br>

[![Open In Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&color=525252)](https://colab.research.google.com/github/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/blob/main/Retrieval_based_Voice_Conversion_WebUI.ipynb)
[![Licence](https://img.shields.io/badge/LICENSE-MIT-green.svg?style=for-the-badge)](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/blob/main/LICENSE)
[![Huggingface](https://img.shields.io/badge/🤗%20-Spaces-yellow.svg?style=for-the-badge)](https://huggingface.co/lj1995/VoiceConversionWebUI/tree/main/)

[![Discord](https://img.shields.io/badge/RVC%20Developers-Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/HcsmBBGyVk)

[**Changelog**](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/blob/main/docs/Changelog_CN.md) | [**FAQ**](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/wiki/%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94) | [**AutoDL: Training AI Singers**](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/wiki/Autodl%E8%AE%AD%E7%BB%83RVC%C2%B7AI%E6%AD%8C%E6%89%8B%E6%95%99%E7%A8%8B) | [**Comparison Experiment Records**](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/wiki/%E5%AF%B9%E7%85%A7%E5%AE%9E%E9%AA%8C%C2%B7%E5%AE%9E%E9%AA%8C%E8%AE%B0%E5%BD%95) | [**Online Demo**](https://modelscope.cn/studios/FlowerCry/RVCv2demo)

[**English**](./docs/en/README.en.md) | [**Simplified Chinese**](./README.md) | [**Japanese**](./docs/jp/README.ja.md) | [**Korean**](./docs/kr/README.kr.md)

## Overview

This project is an easy-to-use voice conversion framework based on VITS. It is designed for simple operation and high-quality voice conversion.

## Usage

### Installation

#### 1. Environment Setup

Ensure you have Python 3.8 or later installed. Install the required dependencies by running:
```bash
pip install -r requirements.txt
```

If you are using the [WebUI Colab Notebook](https://colab.research.google.com/github/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/blob/main/Retrieval_based_Voice_Conversion_WebUI.ipynb), this step is not necessary.

#### 2. Download Pretrained Models

Download the pretrained model files from [Huggingface](https://huggingface.co/lj1995/VoiceConversionWebUI/tree/main/) and place them in the `checkpoints` directory.

- `G_latest.pth`
- `D_latest.pth`
- `f0G_latest.pth`
- `f0D_latest.pth`
- `mapper_pretrain.pth`

### 3. Download RMVPE Pitch Extraction Files

To use the latest RMVPE pitch extraction algorithm, download the required files and place them in the RVC root directory.

- Download [rmvpe.pt](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/rmvpe.pt)

#### Optional: Download RMVPE DML Environment (for AMD/Intel users)

- Download [rmvpe.onnx](https://huggingface.co/lj1995/VoiceConversionWebUI/blob/main/rmvpe.onnx)

### 4. AMD GPU ROCm (Optional, Linux Only)

To run RVC using AMD's ROCm on Linux, install the necessary drivers [here](https://rocm.docs.amd.com/en/latest/deploy/linux/os-native/install.html).

For Arch Linux, use the following command:
```bash
pacman -S rocm-hip-sdk rocm-opencl-sdk
```

For certain GPU models, additional configuration may be required:
```bash
export ROCM_PATH=/opt/rocm
export HSA_OVERRIDE_GFX_VERSION=10.3.0
```

Ensure your current user is part of the `render` and `video` groups:
```bash
sudo usermod -aG render $USERNAME
sudo usermod -aG video $USERNAME
```

## Getting Started

### Direct Start

Start the WebUI using the following command:
```bash
python infer-web.py
```

If you installed dependencies using Poetry, start the WebUI with:
```bash
poetry run python infer-web.py
```

### Using the Integrated Package

Download and extract `RVC-beta.7z`.

#### For Windows Users

Double-click `go-web.bat`.

#### For MacOS Users

```bash
sh ./run.sh
```

### For Intel Users Requiring IPEX (Linux Only)

```bash
source /opt/intel/oneapi/setvars.sh
```

## Reference Projects

- [ContentVec](https://github.com/auspicious3000/contentvec/)
- [VITS](https://github.com/jaywalnut310/vits)
- [HIFIGAN](https://github.com/jik876/hifi-gan)
- [Gradio](https://github.com/gradio-app/gradio)
- [FFmpeg](https://github.com/FFmpeg/FFmpeg)
- [Ultimate Vocal Remover](https://github.com/Anjok07/ultimatevocalremovergui)
- [audio-slicer](https://github.com/openvpi/audio-slicer)
- [Vocal pitch extraction: RMVPE](https://github.com/Dream-High/RMVPE)
  - The pretrained model is trained and tested by [yxlllc](https://github.com/yxlllc/RMVPE) and [RVC-Boss](https://github.com/RVC-Boss).

## Acknowledgements

Thanks to all contributors for their efforts:
<a href="https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI/graphs/contributors" target="_blank">
  <img src="https://contrib.rocks/image?repo=RVC-Project/Retrieval-based-Voice-Conversion-WebUI" />
</a>
