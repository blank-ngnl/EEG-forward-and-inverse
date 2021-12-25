# EEG forward and inverse
## Setup
Install MNE-python
```
conda create --name=mne python=3.8
conda activate mne
conda env update --file environment.yml
pip3 install torch==1.10.1+cu113 torchvision==0.11.2+cu113 torchaudio===0.10.1+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
```