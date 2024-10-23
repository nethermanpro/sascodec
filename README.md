# SASCodec: Semantic Aware Speech Codec

## Getting Started

This is the repository for the SASCodec, which is applied in paper "TransVIP: Speech to Speech Translation System with Voice and Isochrony Preservation".

## Specification of dependencies

### Installation

```bash
git clone https://github.com/descriptinc/audiotools
cd sascodec
pip install .
```

Pretrained checkpoint on CommonVoice 15 dataset is available [here](https://drive.google.com).

### Usage

```python
from sascodec import SASCodec
model = SASCodec.from_pretrained("/path/to/checkpoint")
wav = [...] # load some wav file, shape: (batch, 1, timesteps)
codes = model.encode(wav) # codes, shape: (batch, n_q, timesteps)
reconstructed_wav = model.decode(codes) # reconstructed_wav, shape: (batch, 1, timesteps)
```

### Training

Refer to the script [here](.) for training the model.

## Acknowledgement

The SASCodec model and training script is based on DAC (<https://github.com/descriptinc/descript-audio-codec>) and speechtokenizer (<https://github.com/ZhangXInFD/SpeechTokenizer>). Again, we would like to thank the authors for their valuable contributions and for making their work available as open-source.

## Citation

To cite this repository

```bibtex
@article{le2024transvip,
  title={TransVIP: Speech to Speech Translation System with Voice and Isochrony Preservation},
  author={Le, Chenyang and Qian, Yao and Wang, Dongmei and Zhou, Long and Liu, Shujie and Wang, Xiaofei and Yousefi, Midia and Qian, Yanmin and Li, Jinyu and Zhao, Sheng and others},
  journal={Proceedings of the 38th International Conference on Neural Information Processing Systems (NeurIPS 2024)},
  year={2024}
}
```