## Training and testing codes for SwinIR

Clone repo
----------
```
git clone https://github.com/cszn/KAIR.git
```
```
pip install -r requirement.txt
```



Training
----------

You should modify the json file from [options](https://github.com/cszn/KAIR/tree/master/options) first, for example,
setting ["gpu_ids": [0,1,2,3]](https://github.com/cszn/KAIR/blob/ff80d265f64de67dfb3ffa9beff8949773c81a3d/options/train_msrresnet_psnr.json#L4) if 4 GPUs are used,
setting ["dataroot_H": "trainsets/trainH"](https://github.com/cszn/KAIR/blob/ff80d265f64de67dfb3ffa9beff8949773c81a3d/options/train_msrresnet_psnr.json#L24) if path of the high quality dataset is `trainsets/trainH`.

- Training with `DataParallel` - SwinIR


```python
python main_train_psnr.py --opt options/swinir/train_swinir_denoising_color.json
```


Inference
----------

- Inference on `DataParallel` - SwinIR


```python
python main_test_swinir.py --task color_dn --noise 0 --model_path denoising/swinir_denoising_color_15/models/100000_G.pth --folder_gt testsets/custom_dataset
```


----------
| Method | Original Link |
|---|---|
| DnCNN |[https://github.com/cszn/DnCNN](https://github.com/cszn/DnCNN)|
| FDnCNN |[https://github.com/cszn/DnCNN](https://github.com/cszn/DnCNN)|
| FFDNet | [https://github.com/cszn/FFDNet](https://github.com/cszn/FFDNet)|
| SRMD | [https://github.com/cszn/SRMD](https://github.com/cszn/SRMD)|
| DPSR-SRResNet | [https://github.com/cszn/DPSR](https://github.com/cszn/DPSR)|
| SRResNet | [https://github.com/xinntao/BasicSR](https://github.com/xinntao/BasicSR)|
| ESRGAN | [https://github.com/xinntao/ESRGAN](https://github.com/xinntao/ESRGAN)|
| RRDB | [https://github.com/xinntao/ESRGAN](https://github.com/xinntao/ESRGAN)|
| IMDB | [https://github.com/Zheng222/IMDN](https://github.com/Zheng222/IMDN)|
| USRNet | [https://github.com/cszn/USRNet](https://github.com/cszn/USRNet)|
| DRUNet | [https://github.com/cszn/DPIR](https://github.com/cszn/DPIR)|
| DPIR | [https://github.com/cszn/DPIR](https://github.com/cszn/DPIR)|
| BSRGAN | [https://github.com/cszn/BSRGAN](https://github.com/cszn/BSRGAN)|
| SwinIR | [https://github.com/JingyunLiang/SwinIR](https://github.com/JingyunLiang/SwinIR)|
| VRT | [https://github.com/JingyunLiang/VRT](https://github.com/JingyunLiang/VRT)       |
| DiffPIR | [https://github.com/yuanzhi-zhu/DiffPIR](https://github.com/yuanzhi-zhu/DiffPIR)|

Network architectures
----------
* [USRNet](https://github.com/cszn/USRNet)

  <img src="https://github.com/cszn/USRNet/blob/master/figs/architecture.png" width="600px"/> 

* DnCNN

  <img src="https://github.com/cszn/DnCNN/blob/master/figs/dncnn.png" width="600px"/> 
 
* IRCNN denoiser

 <img src="https://github.com/lipengFu/IRCNN/raw/master/Image/image_2.png" width="680px"/> 

* FFDNet

  <img src="https://github.com/cszn/FFDNet/blob/master/figs/ffdnet.png" width="600px"/> 

* SRMD

  <img src="https://github.com/cszn/SRMD/blob/master/figs/architecture.png" width="605px"/> 

* SRResNet, SRGAN, RRDB, ESRGAN

  <img src="https://github.com/xinntao/ESRGAN/blob/master/figures/architecture.jpg" width="595px"/> 
  
* IMDN

  <img src="figs/imdn.png" width="460px"/>  ----- <img src="figs/imdn_block.png" width="100px"/> 



Testing
----------
|Method | [model_zoo](model_zoo)|
|---|---|
| [main_test_dncnn.py](main_test_dncnn.py) |```dncnn_15.pth, dncnn_25.pth, dncnn_50.pth, dncnn_gray_blind.pth, dncnn_color_blind.pth, dncnn3.pth```|
| [main_test_ircnn_denoiser.py](main_test_ircnn_denoiser.py) | ```ircnn_gray.pth, ircnn_color.pth```| 
| [main_test_fdncnn.py](main_test_fdncnn.py) | ```fdncnn_gray.pth, fdncnn_color.pth, fdncnn_gray_clip.pth, fdncnn_color_clip.pth```|
| [main_test_ffdnet.py](main_test_ffdnet.py) | ```ffdnet_gray.pth, ffdnet_color.pth, ffdnet_gray_clip.pth, ffdnet_color_clip.pth```|
| [main_test_srmd.py](main_test_srmd.py) | ```srmdnf_x2.pth, srmdnf_x3.pth, srmdnf_x4.pth, srmd_x2.pth, srmd_x3.pth, srmd_x4.pth```| 
|  | **The above models are converted from MatConvNet.** |
| [main_test_dpsr.py](main_test_dpsr.py) | ```dpsr_x2.pth, dpsr_x3.pth, dpsr_x4.pth, dpsr_x4_gan.pth```|
| [main_test_msrresnet.py](main_test_msrresnet.py) | ```msrresnet_x4_psnr.pth, msrresnet_x4_gan.pth```|
| [main_test_rrdb.py](main_test_rrdb.py) | ```rrdb_x4_psnr.pth, rrdb_x4_esrgan.pth```|
| [main_test_imdn.py](main_test_imdn.py) | ```imdn_x4.pth```|

[model_zoo](model_zoo)
--------
- download link [https://drive.google.com/drive/folders/13kfr3qny7S2xwG9h7v95F5mkWs0OmU0D](https://drive.google.com/drive/folders/13kfr3qny7S2xwG9h7v95F5mkWs0OmU0D)

[trainsets](trainsets)
----------
- [https://github.com/xinntao/BasicSR/blob/master/docs/DatasetPreparation.md](https://github.com/xinntao/BasicSR/blob/master/docs/DatasetPreparation.md)
- [train400](https://github.com/cszn/DnCNN/tree/master/TrainingCodes/DnCNN_TrainingCodes_v1.0/data)
- [DIV2K](https://data.vision.ee.ethz.ch/cvl/DIV2K/)
- [Flickr2K](https://cv.snu.ac.kr/research/EDSR/Flickr2K.tar)
- optional: use [split_imageset(original_dataroot, taget_dataroot, n_channels=3, p_size=512, p_overlap=96, p_max=800)](https://github.com/cszn/KAIR/blob/3ee0bf3e07b90ec0b7302d97ee2adb780617e637/utils/utils_image.py#L123) to get ```trainsets/trainH``` with small images for fast data loading

[testsets](testsets)
-----------
- [https://github.com/xinntao/BasicSR/blob/master/docs/DatasetPreparation.md](https://github.com/xinntao/BasicSR/blob/master/docs/DatasetPreparation.md)
- [set12](https://github.com/cszn/FFDNet/tree/master/testsets)
- [bsd68](https://github.com/cszn/FFDNet/tree/master/testsets)
- [cbsd68](https://github.com/cszn/FFDNet/tree/master/testsets)
- [kodak24](https://github.com/cszn/FFDNet/tree/master/testsets)
- [srbsd68](https://github.com/cszn/DPSR/tree/master/testsets/BSD68/GT)
- set5
- set14
- cbsd100
- urban100
- manga109


References
----------
```BibTex
@inproceedings{zhu2023denoising, % DiffPIR
title={Denoising Diffusion Models for Plug-and-Play Image Restoration},
author={Yuanzhi Zhu and Kai Zhang and Jingyun Liang and Jiezhang Cao and Bihan Wen and Radu Timofte and Luc Van Gool},
booktitle={IEEE Conference on Computer Vision and Pattern Recognition Workshops},
year={2023}
}
@article{liang2022vrt,
title={VRT: A Video Restoration Transformer},
author={Liang, Jingyun and Cao, Jiezhang and Fan, Yuchen and Zhang, Kai and Ranjan, Rakesh and Li, Yawei and Timofte, Radu and Van Gool, Luc},
journal={arXiv preprint arXiv:2022.00000},
year={2022}
}
@inproceedings{liang2021swinir,
title={SwinIR: Image Restoration Using Swin Transformer},
author={Liang, Jingyun and Cao, Jiezhang and Sun, Guolei and Zhang, Kai and Van Gool, Luc and Timofte, Radu},
booktitle={IEEE International Conference on Computer Vision Workshops},
pages={1833--1844},
year={2021}
}
@inproceedings{zhang2021designing,
title={Designing a Practical Degradation Model for Deep Blind Image Super-Resolution},
author={Zhang, Kai and Liang, Jingyun and Van Gool, Luc and Timofte, Radu},
booktitle={IEEE International Conference on Computer Vision},
pages={4791--4800},
year={2021}
}
@article{zhang2021plug, % DPIR & DRUNet & IRCNN
  title={Plug-and-Play Image Restoration with Deep Denoiser Prior},
  author={Zhang, Kai and Li, Yawei and Zuo, Wangmeng and Zhang, Lei and Van Gool, Luc and Timofte, Radu},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence},
  year={2021}
}
@inproceedings{zhang2020aim, % efficientSR_challenge
  title={AIM 2020 Challenge on Efficient Super-Resolution: Methods and Results},
  author={Kai Zhang and Martin Danelljan and Yawei Li and Radu Timofte and others},
  booktitle={European Conference on Computer Vision Workshops},
  year={2020}
}
@inproceedings{zhang2020deep, % USRNet
  title={Deep unfolding network for image super-resolution},
  author={Zhang, Kai and Van Gool, Luc and Timofte, Radu},
  booktitle={IEEE Conference on Computer Vision and Pattern Recognition},
  pages={3217--3226},
  year={2020}
}
@article{zhang2017beyond, % DnCNN
  title={Beyond a gaussian denoiser: Residual learning of deep cnn for image denoising},
  author={Zhang, Kai and Zuo, Wangmeng and Chen, Yunjin and Meng, Deyu and Zhang, Lei},
  journal={IEEE Transactions on Image Processing},
  volume={26},
  number={7},
  pages={3142--3155},
  year={2017}
}
@inproceedings{zhang2017learning, % IRCNN
title={Learning deep CNN denoiser prior for image restoration},
author={Zhang, Kai and Zuo, Wangmeng and Gu, Shuhang and Zhang, Lei},
booktitle={IEEE conference on computer vision and pattern recognition},
pages={3929--3938},
year={2017}
}
@article{zhang2018ffdnet, % FFDNet, FDnCNN
  title={FFDNet: Toward a fast and flexible solution for CNN-based image denoising},
  author={Zhang, Kai and Zuo, Wangmeng and Zhang, Lei},
  journal={IEEE Transactions on Image Processing},
  volume={27},
  number={9},
  pages={4608--4622},
  year={2018}
}
@inproceedings{zhang2018learning, % SRMD
  title={Learning a single convolutional super-resolution network for multiple degradations},
  author={Zhang, Kai and Zuo, Wangmeng and Zhang, Lei},
  booktitle={IEEE Conference on Computer Vision and Pattern Recognition},
  pages={3262--3271},
  year={2018}
}
@inproceedings{zhang2019deep, % DPSR
  title={Deep Plug-and-Play Super-Resolution for Arbitrary Blur Kernels},
  author={Zhang, Kai and Zuo, Wangmeng and Zhang, Lei},
  booktitle={IEEE Conference on Computer Vision and Pattern Recognition},
  pages={1671--1681},
  year={2019}
}
@InProceedings{wang2018esrgan, % ESRGAN, MSRResNet
    author = {Wang, Xintao and Yu, Ke and Wu, Shixiang and Gu, Jinjin and Liu, Yihao and Dong, Chao and Qiao, Yu and Loy, Chen Change},
    title = {ESRGAN: Enhanced super-resolution generative adversarial networks},
    booktitle = {The European Conference on Computer Vision Workshops (ECCVW)},
    month = {September},
    year = {2018}
}
@inproceedings{hui2019lightweight, % IMDN
  title={Lightweight Image Super-Resolution with Information Multi-distillation Network},
  author={Hui, Zheng and Gao, Xinbo and Yang, Yunchu and Wang, Xiumei},
  booktitle={Proceedings of the 27th ACM International Conference on Multimedia (ACM MM)},
  pages={2024--2032},
  year={2019}
}
@inproceedings{zhang2019aim, % IMDN
  title={AIM 2019 Challenge on Constrained Super-Resolution: Methods and Results},
  author={Kai Zhang and Shuhang Gu and Radu Timofte and others},
  booktitle={IEEE International Conference on Computer Vision Workshops},
  year={2019}
}
@inproceedings{yang2021gan,
    title={GAN Prior Embedded Network for Blind Face Restoration in the Wild},
    author={Tao Yang, Peiran Ren, Xuansong Xie, and Lei Zhang},
    booktitle={IEEE Conference on Computer Vision and Pattern Recognition},
    year={2021}
}
```
