# PyTorch Implementation of TransformersLTE

We present 'Learning To Explain' (LTE) - a novel method for producing explanations by learning explanation masks. The LTE framework introduces an explainer-explainee model, in which the explainer learns to explain and justify the explainee's predictions. We demonstrate LTE's ability to produce explanations for ViT models, where it significantly outperforms state-of-the-art alternatives on multiple explanations and segmentation tests. 

---
## Reproducing results on ViT-Base
---
### Loading Checkpoints:
- Download `checkpoints.zip` from https://drive.google.com/file/d/1AUYAxBgn5hvFbfaNgg73vNjS8PwTZYxV/view?usp=sharing 
- unzip classifier.zip -d ./checkpoints/

### Stage A - pLTE:
Example:
```
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 baselines/ViT/imagenet_seg_eval.py

```

### Stage B - LTE:

Example:
```
CUDA_VISIBLE_DEVICES=0 PYTHONPATH=./:$PYTHONPATH python3 baselines/ViT/imagenet_seg_eval.py

```
