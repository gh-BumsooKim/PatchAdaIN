PatchAdaIN
==========

Official PatchAdaIN implementation of [Patched Arbitary Style Transfer for Local Statistics]() presented on [ICTC2022](https://www.ictc.org/) Workshop on Artificial  Intelligence (IWAI), Oct.19-21, Jeju, Korea.

This code was written by [Bumsoo Kim](https://scholar.google.com/citations?user=JlNb4R8AAAAJ&hl=ko&authuser=1&oi=sra)

<br>

<!-- ![](./figure01.png) -->
<p align=center> <img src="https://user-images.githubusercontent.com/67869508/182145936-3d6f1f5f-965a-4782-ba4b-e09247bd0a11.png"> </p>

Implementation Environment
------------
#### System
- Windows10
- Nvidia GeForce RTX 3090 24GB
- Intel Core i9-12900k / 64GB Memory

#### Library
- Python 3.9
- Pytorch 1.12.0
- torchvision 0.12
- cuda 11.6
- cudnn 8.0

<br>

Usage
-----

### Train

Download pretrained [vgg19_normalized.pth]() for encoder and [decoder.pth]() for decoder <br>
Download [MSCOCO]() for content image and [WikiArt]() for style image

```cmd
python main.py --train True --content_folder $CONTENTDIR --style_folder $STYLEDIR

usage : main.py [-h] [--train TRAIN] [-content_dir CONTENT_DIR]

optional arguments:
 -h, --help
 --input_size INPUT_SIZE
                240 X N
 --patch_loss PATCH_LOSS
                between 0.0 and 1.0
```


### Test
```python
python main.py --test True --content_image $CONTENTIMAGE --style_image $STYLEIMAGE 
```

### Test with Multi style Image
```python
python main.py --test True --content_image $CONTENTIMAGE --style_image $STYLEDIR --n_style_image 4 --style_order 1234
```
