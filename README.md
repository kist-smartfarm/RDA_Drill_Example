# PhytoChamber 데이터를 활용한 응용 실습 예제를 위한 환경 설정.
### 1. Miniforge 혹은 Anaconda 를 활용한 가상환경 구성
> https://github.com/conda-forge/miniforge

##### (예시)

mamba create -n rda python=3.11 -y && mamba activate rda
- 아래 링크를 통해 본인의 환경에 맞는 Pytorch를 설치. (The code requires python>=3.10, as well as torch>=2.3.1 and torchvision>=0.18.1)
> https://pytorch.org/get-started/locally/


#### Meta에서 발표한 SAM2 설치

```bash
git clone https://github.com/facebookresearch/segment-anything-2.git

cd segment-anything-2 & pip install -e .
```
If you are installing on Windows, it's strongly recommended to use [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/install) with Ubuntu.

<hr>

### Download Checkpoints

아래의 명령어를 실행, 스크립트를 통해 모델 weight를 다운로드 받을 수 있음.

```bash
cd checkpoints && \
./download_ckpts.sh && \
cd ..
```

or individually from:

- [sam2_hiera_tiny.pt](https://dl.fbaipublicfiles.com/segment_anything_2/072824/sam2_hiera_tiny.pt)
- [sam2_hiera_small.pt](https://dl.fbaipublicfiles.com/segment_anything_2/072824/sam2_hiera_small.pt)
- [sam2_hiera_base_plus.pt](https://dl.fbaipublicfiles.com/segment_anything_2/072824/sam2_hiera_base_plus.pt)
- [sam2_hiera_large.pt](https://dl.fbaipublicfiles.com/segment_anything_2/072824/sam2_hiera_large.pt)

<hr>

### 2. 추가적으로 설치해야 할 라이브러리

```bash
pip install plantcv numpy==1.26.4 kornia transformers notebook ipywidgets opencv-python timm scipy \
scikit-image tqdm prettytable huggingface_hub
```