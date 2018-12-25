YOLO_v3
=
YOLO_v3 implemented with tensorflow <br>
Support for parallel training and testing <br>

- [x] Group Normalization<br>
- [x] Focal loss<br>
- [x] Soft-NMS(no useful)<br>
- [x] data augmentation<br>
- [x] multi-scale training<br>
- [ ] Single-Shot Object Detection with Enriched Semantics<br>
- [ ] SNIP<br>
## Usage
1. clone YOLO_v3 repository
``` bash
git clone https://github.com/Stinky-Tofu/YOLO_V3.git
```
2. Download dataset <br>
Create a new folder named `data` in the directory where the `YOLO` folder is located, and then create a new folder named `VOC` in the `data/`.<br>
Download [VOC_2012_trainval](﻿http://host.robots.ox.ac.uk/pascal/VOC/voc2012/VOCtrainval_11-May-2012.tar)、[VOC_2007_trainval](﻿http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtrainval_06-Nov-2007.tar)、[VOC_2007_test](﻿http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtest_06-Nov-2007.tar)
,Then put these datasets into `data/VOC`,rename as `2012_trainval`、`2007_trainval`、`2007_test`
3. Train<br>
You should create a new folder named `weights` and put the downloaded
 [yolo_coco_initial.ckpt](https://drive.google.com/drive/folders/1tHhxpmEAM0G34g8YdcDVNJv9s57smJIz)<br>
 into the `weights` folder
``` bash
python train.py
--weights_file, default='yolo_coco_initial.ckpt'
--gpu, default='0'
--batch_size, default='32'
--frozen, default='True'
--learn_rate_init, default='0.001'
```
4. Test<br>
Download the weight file [yolo_416_85%.ckpt](https://drive.google.com/drive/folders/1We_P5L4nlLofR0IJJXzS7EEklZGUb9sz)
```bash
python test.py
--map_calc, default='False'
--weights_file
--gpu, default='0'
```
## mAP on VOC2007<br>
![mAP](https://github.com/Stinky-Tofu/YOLO_V3/blob/master/mAP/results/mAP.png)<br>
## Reference:<br>
paper: <br>
[YOLOv3: An Incremental Improvement](https://arxiv.org/abs/1804.02767)<br>
[Foca Loss for Dense Object Detection](https://arxiv.org/abs/1708.02002)<br>
[Group Normalization](https://arxiv.org/abs/1803.08494)<br>
[Single-Shot Object Detection with Enriched Semantics](https://arxiv.org/abs/1712.00433)<br>
[An Analysis of Scale Invariance in Object Detection - SNIP](https://arxiv.org/abs/1711.08189)<br>

mAP calculate: [mean Average Precision](https://github.com/Cartucho/mAP)<br>
 
## Requirements
. Tensorflow <br>
. Opencv <br>
. Python <br>
. Numpy<br>