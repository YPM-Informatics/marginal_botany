# Leaf bounding boxes  
Custom object detection with Yolov3 ([paper](https://pjreddie.com/media/files/papers/YOLOv3.pdf)), using [AlexeyAB's](https://github.com/AlexeyAB/darknet) framework. Training set consisted of 2898 annotated images. Starting weights taken from `yolov3.weights`. 

## Installation 
```
$ git clone https://github.com/etowahs/darknet.git
$ cd darknet
$ make                   <-- for Linux only
```
If you have CUDA installed on your computer, you may want to have `GPU=1` in Makefile to have faster detection. See addtional instructions for [Linux](https://github.com/AlexeyAB/darknet#how-to-compile-on-linux-using-make) and [Windows](https://github.com/AlexeyAB/darknet#how-to-compile-on-windows-using-cmake-gui). 

Download trained weights from [here](https://drive.google.com/file/d/1KaBpxZqnR4qs2xdPLNZNzchWHcRC1Y5J/view?usp=sharing) (235MB) and place it in the darknet folder. 

## Detecting Leaves 
To run the detector on a single image:

```
$ cd darknet 
$ ./darknet detector test custom/darknet.data custom/cfg/custom.cfg /location/to/weights/custom_5000.weights -ext_output my-image.jpg
```
To run the detector on an entire folder of images, create a .txt file containing the file locations of all the images. Ex. my-imgs.txt
```
$ ./darknet detector test custom/darknet.data custom/cfg/custom.cfg /location/to/weights/custom_5000.weights -ext_output < my-imgs.txt > output.txt
```

