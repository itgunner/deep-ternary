This repository contains the source code for the paper titled "Deep Learning Sparse Ternary Projections For Compressed Sensing of Images"

# Prerequisites
```
- Tensorflow version 1.2.1
- Numpy version 1.12.1 
- h5py version 2.7.0
- opencv (cv2) version 2.4.11
```

# Usage
### Prepare training data
Currently, my dataset of patches is not too big so during training, a DataLoader instance will load all the patches into memory to feed the network. 
To train with your own data, you may need to create a training set of image patches and store it as a hdf5 database.
Alternatively, for can write your own DataLoader to load and feed your network from your own dataset.

### Configurations
The configs.py file sets all the default configurations and hyper-parameters.
There are some other hyperparameters inside train.py and test.py
To use your own configurations, you can either edit these files, or put your configurations as flags

For example:
```
python train.py --n_epochs=100 --initial_lr=0.005
```

### Training
After preparing your dataset and set all the necessary hyper-parameters, you are ready to train your model.
Run train.py, together with our hyper-parameters, to start the training:
```
python train.py --output_basedir=output
```
The trained model will be saved into output/snapshots 

### Testing
After training the model, you can test it with your images using the test function.

```
python test.py --test_folder=test_images
```

All images (jpg, png, tif) inside the test folder will be used for evaluation.

# License
This project is licensed under the MIT License - see the LICENSE.md file for details

# Reference
If you find the source code useful, please cite us:
```
D. M. Nguyen and E. Tsiligianni and N. Deligiannis, "Deep Learning Sparse Ternary Projections for Compressed Sensing of Images", IEEE Global Conference on Signal and Information Processing (GlobalSIP) 2017
```