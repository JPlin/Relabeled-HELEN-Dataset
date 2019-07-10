# The HELEN* Dataset

The HELEN* dataset is a rectified version of the original [HELEN dataset](http://pages.cs.wisc.edu/~lizhang/projects/face-parsing/SmithCVPR2013_dataset_original.zip).

File structure:
```python
train/ # the training set
    xxx_image.jpg # the face image
    xxx_label.png # the mask annotations
    xxx_viz.jpg   # annotation visualization
test/ # the testing set (in original size)
    ...
test_resize/ # the testing set (resized)
    ...
```

All images in `train/` come from the [original HELEN](http://pages.cs.wisc.edu/~lizhang/projects/face-parsing/SmithCVPR2013_dataset_original.zip). We relabeled the hair and facial skin regions in `train/`. Annotations in `test/` also come from the [original HELEN](http://pages.cs.wisc.edu/~lizhang/projects/face-parsing/SmithCVPR2013_dataset_original.zip). While annotations in `test_resize/` comply with the [resized HELEN](http://pages.cs.wisc.edu/~lizhang/projects/face-parsing/SmithCVPR2013_dataset_resized.zip).


Mask annotation can be loaded by
```python
import cv2
labels = cv2.imread('xxx_label.png', cv2.IMREAD_GRAYSCALE)
```

Meaning of annotation values:
```
0: background
1: facial skin
2: left brow (viewer side)
3: right brow
4: left eye
5: right eye
6: nose
7: upper lip
8: inner mouth
9: lower lip
10: hair
```

F scores can be calculated using `f1_score.py`.

## Citation

If you find the dataset useful, please consider citing
```latex
@inproceedings{lin2019face,
  title={Face Parsing with RoI Tanh-Warping},
  author={Lin, Jinpeng and Yang, Hao and Chen, Dong and Zeng, Ming and Wen, Fang and Yuan, Lu},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={5654--5663},
  year={2019}
}
```