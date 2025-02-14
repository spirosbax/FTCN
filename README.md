# Exploring Temporal Coherence for More General Video Face Forgery Detection(FTCN) 

Yinglin Zheng, Jianmin Bao, Dong Chen, Ming Zeng, Fang Wen

Accepted by ICCV 2021

### [Paper](https://arxiv.org/abs/2108.06693)  

## Abstract
> Although current face manipulation techniques achieve impressive performance regarding quality and controllability, they are struggling to generate temporal coherent face videos. In this work, we explore to take full advantage of the temporal coherence for video face forgery detection. To achieve this, we propose a novel end-to-end framework, which consists of two major stages. The first stage is a fully temporal convolution network (FTCN). The key insight of FTCN is to reduce the spatial convolution kernel size to 1, while maintaining the temporal convolution kernel size unchanged. We surprisingly find this special design can benefit the model for extracting the temporal features as well as improve the generalization capability. The second stage is a Temporal Transformer network, which aims to explore the long-term temporal coherence. The proposed framework is general and flexible, which can be directly trained from scratch without any pre-training models or external datasets. Extensive experiments show that our framework outperforms existing methods and remains effective when applied to detect new sorts of face forgery videos.


# Setup
```
conda env create -f environment.yml
conda activate ftcn
```

then install dependencies for the experiment:

```
python -m pip install -r requirements.txt
```

# Test

## Inference Using Pretrained Model on Raw Video
Download `FTCN+TT` model trained on FF++ from [here](https://github.com/yinglinzheng/FTCN/releases/download/weights/ftcn_tt.pth) and face detector checkpoint from  [here](http://github.com/yinglinzheng/face_weights/releases/download/v1/mobilenet0.25_Final.pth) and place them under `./checkpoints` folder
```bash
python test_on_raw_video.py examples/shining.mp4 output
```
the output will be a video under folder `output` named `shining.avi`

![](./examples/shining.gif)

# Acknowledgments

This code borrows heavily from [SlowFast](https://github.com/facebookresearch/SlowFast).

The face detection network comes from [biubug6/Pytorch_Retinaface](https://github.com/biubug6/Pytorch_Retinaface).

The face alignment network comes from [cunjian/pytorch_face_landmark](https://github.com/cunjian/pytorch_face_landmark).



# Citation
If you use this code for your research, please cite our paper.
```
@inproceedings{zheng2021exploring,
  title={Exploring Temporal Coherence for More General Video Face Forgery Detection},
  author={Zheng, Yinglin and Bao, Jianmin and Chen, Dong and Zeng, Ming and Wen, Fang},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision},
  pages={15044--15054},
  year={2021}
}
```
