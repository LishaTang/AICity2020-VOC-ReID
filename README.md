# VOC-ReID: Vehicle Re-identification based on Vehicle-Orientation-Camera

This repo includes the 2st place solution for [AICity2020](https://www.aicitychallenge.org/) Challenge ReID track. 
[Our paper](http://arxiv.org/abs/2004.09164)


## Introduction
Our work aims to eliminate the bias posed by similar background and shape

This project is mainly based on [reid-strong-baseline](https://github.com/michuanhaohao/reid-strong-baseline) 
and [deep-person-reid](https://github.com/KaiyangZhou/deep-person-reid)


## TODO
- [x] FP16 training (30% faster with no precision drop)
- [x] more metric learning methods (GeM, arcface, circle loss, batch_soft)
- [x] more backbones (OSNet, ResNest, RegNet)

## requirement
1. pytorch>=1.2.0
2. yacs
3. [apex](https://github.com/NVIDIA/apex) (optional for FP16 training)
````
$ git clone https://github.com/NVIDIA/apex
$ cd apex
$ pip install -v --no-cache-dir --global-option="--cpp_ext" --global-option="--cuda_ext" ./
````
4. python>=3.7
5. cv2


## Reproduce the result on AICity 2020 Challenge
Please see [AICity2020.md](AICity2020.md) for details.


## Train
1. Vehicle ReID
2. Orientation ReID
3. Camera ReID

## Test

## Performance
Ablation study on AICity 2020 validation dataset

|method|mAP|Rank1|comment|
|------|---|-----|-------|
|BagOfTricks|21.6%|42.1%|[reid-strong-baseline](https://github.com/michuanhaohao/reid-strong-baseline)|
|+Arcface|26.2%|46.7%|Arcface loss|
|+Circle|29.7%|50.8%|circle loss|
|+Syn|39.5%|64.0%|Syn denotes Synthetic dataset VehicleX|
|WeaklyAug|44.4%|65.3%|WeaklyAug denotes weakly supervised crop augmentation|
|+Orientation|47.0%|70.5%|penalized by Orientation ReID|
|+Camera|50.8%|75.5%|penalized by Camera ReID|

 AICITY2020 Challange Track2 Leaderboard
 
 |TeamName|mAP|Link|
 |--------|----|-------|
 |Baidu-UTS|84.1%|[code](https://github.com/layumi/AICIty-reID-2020)|
 |**RuiYanAI(ours)**|78.1%|
 |DMT|73.1%|[code](https://github.com/heshuting555/AICITY2020_DMT_VehicleReID)|
 
 
 
 Results on VeRi
 
 |method|mAP|Rank1|comment|
 |------|----|----|-----|
 |ResNet50_ibn_a|78.6%|95.9%|P=4,K=16,Size=[256, 256]|
 |+Orientation|79.7%|96.3%| |
 


## Citation
If you find our work helpful, please cite [it](http://arxiv.org/abs/2004.09164)
```
@inproceedings{he2020multi,
 title={VOC-ReID: Vehicle Re-identification based on Vehicle-Orientation-Camera},
 author={Zhu, Xiangyu and Luo, Zhenbo and Fu, Pei and Ji, Xiang},
 booktitle={Proc. CVPR Workshops},
 year={2020}
}
```