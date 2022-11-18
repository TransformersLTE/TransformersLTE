# PyTorch Implementation of TransformersLTE

We present 'Learning To Explain' (LTE) - a novel method for producing explanations by learning explanation masks. The LTE framework introduces an explainer-explainee model, in which the explainer learns to explain and justify the explainee's predictions. We demonstrate LTE's ability to produce explanations for ViT models, where it significantly outperforms state-of-the-art alternatives on multiple explanations and segmentation tests. 


## Reproducing results on ViT-Base - Pertubations Metrics
---
### Loading Checkpoints:
- Download `checkpoints.zip` from https://drive.google.com/file/d/1AUYAxBgn5hvFbfaNgg73vNjS8PwTZYxV/view?usp=sharing 
- unzip classifier.zip -d ./checkpoints/

These checkpoints are important for reproducing the reults.

### Stage A - pLTE:
Example:
```
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 ./main/seg_classification/run_seg_cls.py

```

### Stage B - LTE:

Example:
```
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 ./main/seg_classification/run_seg_cls_opt.py

```
## Reproducing results on ViT-Base - Segmentation Results
---
### Download ImagenetDataset for segmentaion:
- Download imagenet_dataset [Link to download dataset](http://calvin-vision.net/bigstuff/proj-imagenet/data/gtsegs_ijcv.mat)
- Download the COCO_Val2017 [Link to download dataset](https://cocodataset.org/#download)
- Download Pascal_val_2012 [Link to download dataset](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/index.html)

- Move all datasets to ./data/

### Stage A - pLTE:
Example:
```
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 ./main/segmentation_eval/seg_stage_a.py

```

### Stage B - LTE:

Example:
```
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 ./main/segmentation_eval/seg_stage_b.py

```
