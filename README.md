# Urban Radiance Field Representation with Deformable Neural Mesh Primitives

## Datasets
We conduct experiments on two outdoor datasets: KITTI-360 dataset, Waymo-Open-Dataset.
Please refer to preprocess/README.md for more details.

## Environments

1. Compile fairnr.
```
python setup.py build_ext --inplace
```

2. Main requirements:
- CUDA (tested on cuda-11.1)
- PyTorch (tested on torch-1.9.1)
- [pytorch3d](https://pytorch3d.org/)
- [torchsparse](https://github.com/mit-han-lab/torchsparse)

3. Other requirements are provided in `requirements.txt`

## Training
1. Optimize geometry using our pre-trained auto-encoder by running `sh scripts/train_${DATASET}_geo.sh`. (Please specify `SEQUENCE`,`DATA_ROOT`,`LOG_DIR` and `CKPT_DIR` in the script.)

2. Train radiance field by running `sh scripts/train_${DATASET}_render.sh`. (Please specify `SEQUENCE`,`DATA_ROOT`,`LOG_DIR`, `CKPT_DIR` and `PRETRAINED_GEO` in the script.)

## Evaluation

We provide pre-trained weights of a single sequence of KITTI-360 dataset in `pretrained/` for evaluation.
You can run `scripts/test_kitti360.sh` for evaluation. (Please specify `SAVE_DIR` and `DATA_ROOT` in the script.)

## Other demos

### Texture editing
Original

<img src="https://github.com/FanLu97/DNMP-dev/blob/main/demos/demo-edit-raw.gif" width="50%" alt="Original" />

Edited Sample 1

<img src="https://github.com/FanLu97/DNMP-dev/blob/main/demos/demo-edit-1.gif" width="50%" alt="Edited Sample 1" />

Edited Sample 2

<img src="https://github.com/FanLu97/DNMP-dev/blob/main/demos/demo-edit-2.gif" width="50%" alt="Edited Sample 2" />