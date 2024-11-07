# SimpleBEV

This method performs 3D object detection in the BEV space using two separate branches that encoder camera and LiDAR inputs into a unified BEV space. It first strengthen the LiDAR-based encoder by fusing the multi-level BEV features derived from different stages of the sparse convolution and increasing the channel number. To further exploit the information from the camera, we introduce an auxiliary prediction branch using only the BEV features from the camera encoder during training. Moreover, we employ the multi-modal GT-Paste algorithm to alleviate the class imbalance problem. The model is trained without CBGS. This submission assembles several models with different voxel sizes and BEV sizes. Each model performs test-time augmentation during the evaluation.

## Results
### 3D Object Detection (on nuScenes test)

|   Model   | mAP  | NDS  |
| :-------: | :--: | :--: |
| SimpleBEV |75.67 | 77.60|

### 3D Object Detection (on nuScenes val)

|   Model   | mAP  | NDS  |
| :-------: | :--: | :--: |
| SimpleBEV-704(ConvNext-tiny-nocbgs) | 69.78 | 71.47 |
| SimpleBEV-1600(ConvNext-Base-nocbgs)| 70.96 | 73.47 |

## Get Started

### Environment
This implementation is build upon [mmdetection3d](https://github.com/open-mmlab/mmdetection3d), please follow the steps in [install.md](./docs/install.md) to prepare the environment.

### Data
Please follow the official instructions of mmdetection3d to process the nuScenes dataset.(https://mmdetection3d.readthedocs.io/en/latest/datasets/nuscenes_det.html)


## Acknowledgement
Many thanks to the following open-source projects:
* [mmdetection3d](https://github.com/open-mmlab/mmdetection3d)

## Reference

```bibtex
@{author={Zhaoyun, ZhengPeiru, Gongzhan, Zhuhong}}
```