# Install pytorch on Ubuntu with Anaconda environment 
 I used Ubuntu 18.04
# Step 1.1 Need to install anaconda 
[Download Anaconda for ubuntu](https://www.anaconda.com/download/)
    
#### step 1.2 Run the Anaconda Script
    $ cd Downloads    
    $ bash Anaconda3-5.3.0-Linux-x86_64.sh
#### Step 1.2 output
 
    Output
    Welcome to Anaconda3-5.3.0
    In order to continue the installation process, please review the license
    agreement.
    Please, press ENTER to continue
    >>>
    ...
    Do you approve the license terms? [yes|no]
type **yes**
#### Step 1.3 Complete Installation Process
    Output
    Anaconda3 will now be installed into this location:
    /home/borhan/anaconda3
    
      - Press ENTER to confirm the location
      - Press CTRL-C to abort the installation
      - Or specify a different location below
    
    [/home/borhan/anaconda3] >>>
type **yes**    
#### Step 1.4 Select Options
    Output
    ...
    installation finished.
    Do you wish the installer to prepend the Anaconda3 install location
    to PATH in your /home/borhan/.bashrc ? [yes|no]
    [no] >>>
type **yes** 
#### VScode Install
type **no**

#### Step 1.5 Activate Installation
    $ source ~/.bashrc
#### Step 1.6 Test Installation
    $ conda list   
**You will ses some output** 

    # packages in environment at /home/borhan/anaconda3:
    #
    # Name                    Version                   Build  Channel
    _ipyw_jlab_nb_ext_conf    0.1.0            py36he11e457_0  
    alabaster                 0.7.10           py36h306e16b_0  
    anaconda                  5.2.0                    py36_3 
#### Step 1.7 Set Up Anaconda Environments       
     $ conda create --name pyTorch python=3
#### Step 1.8 Activate Anaconda Environments
    $ source activate pyTorch    
**Output**

    (pyTorch) borhan@ubuntu:~$     
#### Step 1.9 checking the python version

    (pyTorch) borhan@ubuntu:~$ python --version
**Output**

    Python 3.7
#### Step 1.10  Inspect all of the environments you have set up with this command:
    $ conda info --envs
    
**Output**

    # conda environments:
    #
    base                     /home/borhan/anaconda3
    pyTorch                * /home/borhan/anaconda3/envs/pyTorch      
    
# Step 2.1 Install Pytorch
**No CUDA**

    $ conda install pytorch-cpu torchvision-cpu -c pytorch
**With CUDA 9.0**    

    $ conda install pytorch torchvision -c pytorch
[You can found your command from here](https://pytorch.org/get-started/locally/)  
    
**Take little time (depend on internet speed) for install many library. you can go for tea break**
 
 
    $
                    
 #### 2.2 Test pytorch
    $ python3
    import torch
    print(torch.__version__)
**Output**

    0.4.1 or latest 
# Step 3.1 Install OpenCV    
    $ conda install -c conda-forge opencv 
    $ conda install -c conda-forge/label/broken opencv
#### 3.2  Test OpenCV  
    $ python3
    import cv2
    print(cv2.__version__) 
**Output**
    
    3.4.2    
# Step 3.1 Install TensorFlow
    $ conda install -c intel tensorflow
    
#### 3.2  Test TensorFlow
    $ python3
    import tensorflow
    print(tensorflow.__version__) 
**Output**
    
    1.10.0    
    
# Last step test full install (pytorch, OpenCV and tensorflow)
    import torch
    from __future__ import print_function
    import cv2
    import tensorflow
    print("Torch version: ",torch.__version__)
    print("OpenCV version",cv2.__version__)
    print("TensorFlow version",tensorflow.__version__)
    print(torch.rand(5,4))
    torch.cuda.is_available()   
**Output**
    
    Torch version:  0.4.1
    OpenCV version 3.4.2
    TensorFlow version 1.10.0
    tensor([[0.2159, 0.6831, 0.0893, 0.7964],
            [0.3756, 0.5890, 0.7941, 0.3761],
            [0.8911, 0.6263, 0.1474, 0.4778],
            [0.4070, 0.9507, 0.7599, 0.9507],
            [0.3709, 0.5526, 0.6739, 0.8450]])
    False
    
# Thanks         
# Usefull command
**List all env**

    $ conda env list
**Active env**
    
    $ source activate pyTorch    

# This topic only for NVIDA GPU user only    
#### if cuda is installed with your conda ??
    import torch
    print(torch.version.cuda) 
**Output**
    
    9.0.176       
# Nvidia driver 
open the **additional-drivers** app, search for it in the dash, or in **software and updates**
select **NVIDIA binary driver**
Run a command 
    
    sudo apt install nvidia-cuda-toolkit
    
[Reference link](https://discuss.pytorch.org/t/pytorch-and-cuda-9-1/13126)   
