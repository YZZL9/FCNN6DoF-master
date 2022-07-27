# FCNN6DoF-master
## Requirements
This code has been tested with
* CUDA 10.0 & cuDNN 7.41 
* Python 3.5
* Tensorflow 1.14.0
* Keras 2.3.0

## Datasets
* CAMERA Dataset: [Training](http://download.cs.stanford.edu/orion/nocs/camera_train.zip)/[Test](http://download.cs.stanford.edu/orion/nocs/camera_val25K.zip)/[IKEA_backgrounds](http://download.cs.stanford.edu/orion/nocs/ikea_data.zip)/[Composed_depths](http://download.cs.stanford.edu/orion/nocs/camera_composed_depth.zip)

* Real Dataset: [Training](http://download.cs.stanford.edu/orion/nocs/real_train.zip)/[Test](http://download.cs.stanford.edu/orion/nocs/real_test.zip)
* Ground truth pose annotation (for an easier evaluation): [Val&Real_test](http://download.cs.stanford.edu/orion/nocs/gts.zip)
* [Object Meshes](http://download.cs.stanford.edu/orion/nocs/obj_models.zip)

You can download the files and store them under data/.

## Pretrain weights
You can find the following checkpoints in this [download link](http://download.cs.stanford.edu/orion/nocs/ckpts.zip):
* NOCS RCNN jointly trained on CAMERA, Real & MS COCO with 32 bin classification setting
* NOCS RCNN jointly trained on CAMERA, Real & MS COCO with regression setting
* Mask RCNN pretrained on MS COCO dataset 

You can download the checkpoints and store them under logs/.

## Training
```
# Train a new model from pretrained COCO weight
python3 train.py
```

## Detection and evaluation
```
# Detect using a checkpoint
python3 detect_eval.py --mode detect --ckpt_path=/logs/ckpt --draw

# Evaluate a checkpoint
python3 detect_eval.py --mode eval --ckpt_path=/output/ckpt 
```




