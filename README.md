# PyTorch Implementation of LTE Framework for Vision Transformer

We present 'Learning To Explain' (LTE) - a novel method for producing explanations by learning explanation masks. The LTE framework introduces an explainer-explainee model, in which the explainer learns to explain and justify the explainee's predictions. We demonstrate LTE's ability to produce explanations for ViT models, where it significantly outperforms state-of-the-art alternatives on multiple explanations and segmentation tests. 


## Reproducing results on ViT-Base & ViT-Small - Pertubations Metrics
---
### Loading Checkpoints:
- Download `checkpoints.zip` from https://drive.google.com/file/d/1AUYAxBgn5hvFbfaNgg73vNjS8PwTZYxV/view?usp=sharing 
- unzip classifier.zip -d ./checkpoints/ (after unzipping, the checkpointes should be in the corresponding folders based on the backbone's type (`vit_base` / `vit_small`))

These checkpoints are important for reproducing the results, also, the paths and the ViT `model_name` in the config file should be edited based on the running environment.

All explanation metrics can be calculated using the mask files created during the LTE procedure.

### LTE:

Example:
```python
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 ./main/seg_classification/run_seg_cls_opt.py
```
### pLTE:

Example:

```python
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 ./main/seg_classification/run_seg_cls.py

```



## Reproducing results on ViT-Base & ViT-Small - Segmentation Results

---
### Download the segmentaion datasets:
- Download imagenet_dataset [Link to download dataset](http://calvin-vision.net/bigstuff/proj-imagenet/data/gtsegs_ijcv.mat)
- Download the COCO_Val2017 [Link to download dataset](https://cocodataset.org/#download)
- Download Pascal_val_2012 [Link to download dataset](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/index.html)

- Move all datasets to ./data/

### pLTE:

Example:
```python
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 ./main/segmentation_eval/seg_stage_a.py

```

### LTE:

Example:
```python
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 ./main/segmentation_eval/seg_stage_b.py

```
