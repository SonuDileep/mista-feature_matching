# mista-feature_matching

# Mista: Fast and Lightweight Semi-Dense Local Feature Matching

**Sonu Dileep**, Colorado State University

WACV 2027 Workshops (CALIPOSE)

<!-- Optional: upload the teaser figure to assets/teaser.jpg and uncomment the line below. -->
<!-- <p align="center"><img src="assets/teaser.jpg" width="60%"></p> -->

## Overview

Mista is a coarse-to-fine semi-dense matcher that performs all self- and cross-attention at 1/64 of the input resolution, in a compact bottleneck where global interaction between the two images costs almost nothing. Global context at high resolution is provided by Fourier token mixing, which gives every feature a global receptive field without pairwise token comparison. An anchored refinement module brings the matches to sub-pixel accuracy.

Mista has 4.9M parameters and runs in 32.0 ms per 832×832 image pair on an RTX 4090. It is trained on MegaDepth only and evaluated zero-shot on ScanNet.

## Results

Relative pose estimation (AUC). Runtime for one 832×832 pair on an RTX 4090, fp32.

| Benchmark | AUC@5° | AUC@10° | AUC@20° |
|---|---|---|---|
| MegaDepth-1500 | 62.4 | 75.9 | 85.4 |
| ScanNet-1500 (zero-shot) | 21.4 | 39.5 | 55.5 |

Homography estimation on HPatches (corner-error AUC).

| @3px | @5px | @10px |
|---|---|---|
| 67.3 | 76.7 | 85.9 |

| Params (M) | Time (ms) |
|---|---|
| 4.9 | 32.0 |

## Code

Code and pretrained weights will be released here soon.

## Citation

```bibtex
@inproceedings{dileep2027mista,
  title     = {Mista: Fast and Lightweight Semi-Dense Local Feature Matching},
  author    = {Dileep, Sonu},
  booktitle = {Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision (WACV) Workshops},
  year      = {2027}
}
```
