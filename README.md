# Caffe_VDSR
This is a implementation of ["Accurate Image Super-Resolution Using Very Deep Convolutional Networks"](http://arxiv.org/abs/1511.04587) (CVPR 2016 Oral Paper) in caffe.

## Instruction
VDSR (Very Deep network for Super-Resolution) is an end-to-end network with 20 convolution layers for single image super-resolution. The performance of VDSR is better than other state-of-the-art SISR methods, such as [SRCNN](http://mmlab.ie.cuhk.edu.hk/projects/SRCNN.html), [A+](http://www.vision.ee.ethz.ch/~timofter/ACCV2014_ID820_SUPPLEMENTARY/) and [CSCN](http://www.ifp.illinois.edu/~dingliu2/iccv15/) ([My implementation of CSCN](https://github.com/huangzehao/SCN_Matlab)).

## Dependencies
### Train
- [Caffe](http://caffe.berkeleyvision.org/)

### Test
- [MatConvNet](http://www.vlfeat.org/matconvnet/)

## Usage
### Train

1. Place the "Train" folder into "($Caffe_Dir)/examples/", and rename "Train" to "VDSR"

2. Open MATLAB and direct to ($Caffe_Dir)/example/VDSR, run 
"generate_train.m" and "generate_test.m" to generate training and test data. (Code from SRCNN)

3. To train VDSR, run
./build/tools/caffe train --solver examples/VDSR/VDSR_solver.prototxt

4. Set clip_gradients in VDSR_solver.prototxt to solve gradient explosion problem, 0.1 or 1 is a good choice

5. Change the learning rate when the error plateaus

### Test

1. "Demo_SR_Conv.m" is a simple test code. Just run it and you will get the result.

2. "VDSR_170000.mat" is a model trained by myself.

## Different from original paper
## Training Dataset
My implementation: 91 images (with data augumentation and only factor 2) 

Original paper: 291 images (with data augumentation and factor 2, 3 and 4)
## Multi scale
My implementation: Casade of 2x to generate 3x and 4x result

Original paper: Multi scale in one model
## Training Time
My implementation: about 30 epoch

Original paper: about 80 epoch
## Performance
## References
Please cite [1] if you use this code in your work, thank you!

[1] Jiwon Kim, Jung Kwon Lee, Kyoung Mu Lee, Accurate Image Super-Resolution Using Very Deep Convolutional Networks, arXiv:1511.04587, 2015
