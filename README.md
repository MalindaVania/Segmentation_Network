## Medical Image Segmentation using paired and unpaired trainingsamples ##

 **Prerequisites**
 1. Python 3.5.4
 2. Pytorch 0.3.1
 3. Visdom and dominate
 
 **Training**
 1. Prepare the datasets 
 2. Create a folder name *datasets* with the subfolder structures as given in this repo.
 3. Keep the paired data in *train*-subfolder and unpaired data in *trainA* and *trainB* subfolders.
 4. Then run: *python train.py --dataroot ./datasets --model cycle_gan --dataset_mode unaligned --which_model_netG resnet_9blocks --which_direction AtoB --super_epoch 50 --super_epoch_start 0 --super_mode aligned --super_start 1 --name mygan_70 --no_dropout*
 
**Testing**
 1. Prepare the test datasets
 2. Keep the test data in *testA* and *testB* subfolders within *datasets* folder.
 3. Then run: *python test.py --dataroot ./datasets --model cycle_gan --dataset_mode unaligned --which_model_netG resnet_9blocks --which_direction AtoB --name mygan_70 --how_many 100*
 
 **Training Tips:**
 1. With less paired data, increase the --super_epoch value for better results. 
 2. With No paired data, set --super_start 0. 
 3. For no unpaired data, set --super_epoch and --niter to same value. The VGG loss is not included.
 
 **If you are using this implementation for your research work then please cite us as:** 

```
#Citation 

@article{Vania+Lee,
  title={Lumbar Vertebrae Synthetic Segmentation in Computed Tomography Images Using Hybrid Deep Generative Adversarial Networks},
  author={Vania, Malinda and Lee, Deukhee},
  journal={submitted to EMBC 2020
  year={2020
}

```
```
Related Work

1. Ian J. Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, Yoshua Bengio "Generative Adversarial Networks", in NIPS 2014. 
2. Phillip Isola, Jun-Yan Zhu, Tinghui Zhou, and Alexei A. Efros. "Image-to-Image Translation with Conditional Adversarial Networks", in CVPR 2017.
3. J. Y. Zhu, T. Park, P. Isola, and A. A. Efros. "Unpaired image-to-image translation using cycle-consistent adversarial networks",
```
**NOTE:** Code borrows heavily from [pix2pix](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix)

