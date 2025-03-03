# [**Compressing Deep Image Super-resolution Models**](https://arxiv.org/abs/2401.00523)
### [**Yuxuan Jiang**](https://YuxuanJJ.github.io/), Jakub Nawała, Fan Zhang, David Bull
### Accepted in [**PCS2024**](https://signalprocessingsociety.org/blog/pcs-2024-2024-picture-coding-symposium).

This code is built based on [**BasicSR**](https://github.com/XPixelGroup/BasicSR), where more information can be found to help use this code.

## Preparing datasets
### Training sets:
[[DIV2K]](https://data.vision.ee.ethz.ch/cvl/DIV2K/) More details are in [DatasetPreparation.md](https://github.com/XPixelGroup/BasicSR/blob/master/docs/DatasetPreparation.md#image-super-resolution)
### Test sets: 
[[Set5]](https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u)
[[Set14]](https://drive.google.com/drive/folders/1B3DJGQKB6eNdwuQIhdskA64qUuVKLZ9u)

## Workflow
<img src="https://github.com/Pikapi22/Pikapi22.github.io/blob/main/CDISM/Picture5_3.svg" alt="Paper" width="80%">


## Pruning:
### SwinIR
```
python .\basicsr\prune.py -opt .\options\train\SwinIR\prune_SwinIRlight_SRx2.yml
```

### EDSR
```
python .\basicsr\prune.py -opt .\options\train\EDSR\prune_EDSR_Mx2.yml
```

## KD:
### SwinIR
```
python .\basicsr\distill.py -opt .\options\train\SwinIR\train_SwinIRmini_SRx2_scratch_kd.yml
```

### EDSR
```
python .\basicsr\distill.py -opt .\options\train\EDSR\distill_EDSR_Minix2_KD.yml 
```

## Evaluation (on test sets)
### SwinIR
```
python .\basicsr\test.py -opt .\options\test\SwinIR\test_EDSR_Mx2.yml
```

### EDSR
```
python .\basicsr\test.py -opt .\options\test\EDSR\test_EDSR_Minix2.yml
```

## Results
<img src="https://github.com/Pikapi22/Pikapi22.github.io/blob/main/CDISM/performancetradeoff.svg" alt="Paper" width="60%">

## Citation
```
@article{jiang2023compressing,
  title={Compressing Deep Image Super-resolution Models},
  author={Jiang, Yuxuan and Nawala, Jakub and Zhang, Fan and Bull, David},
  journal={arXiv preprint arXiv:2401.00523},
  year={2023}
}
```
