# VRDL_HW4

if you want to demo, you can go to here (all the weights and models will be downloaded):
https://colab.research.google.com/drive/1Ecm7Dw1anKenOGB_IomBCMRAfpyZe894?usp=sharing

Data preparing
-------------
Just download the zip file dataset from the link provided by TA and unzip it
```bash
import glob
!gdown https://drive.google.com/uc?id=1GL_Rh1N-WjrvF_-YOKOyvq0zrV6TF4hb
!unzip -o -q "/content/datasets.zip" -d "/content/"
```
and then mkdir a folder name dataset in VRDL_HW4/ which should be like
```bash
└──  VRDL_HW4
	└── dataset
	  	└── HW4_datasets
			├──train
				├──100075.png
				├──...
				
			└── valid
				├──100075.png
				├──...
```
I use the the whole trainig dataset also be a validation dataset


Training
-------------

installation and download the 
```bash
!git clone https://github.com/cghero-fi/VRDL_HW4.git
```
and easily traing by the command
```bash
!python3 main.py --dataset HW4_datasets --cuda --gpuids 0 --upscale_factor 3 --crop_size 128 --batch_size 64 --test_batch_size 16 --epochs 200
```
Testing (Can demo in Colab link)
-------------
if you want to use my weights you can download by this command
```bash
import glob
!gdown https://drive.google.com/uc?id=1JPnQEDVRoUUQXpAhf5DT53kHc-xbgx9x
```
Weights download(if you use colab to demo, you don’t need to download in here):
https://drive.google.com/file/d/1JPnQEDVRoUUQXpAhf5DT53kHc-xbgx9x/view?usp=sharing

and use this command to scaling per image (00.png for example)
```bash
!python3 run.py --cuda --gpuids 0 --scale_factor 3 --model final.pth --input_image /content/testing_lr_images/testing_lr_images/00.png --output_filename output/00_pred.png
```
--model final.pth can replaced by the weight you trained yourself
