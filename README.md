# Forest-Buddy-Server
Forest Buddy Server 

## Forest Buddy Install 
Prerequisites
- Windows 10 | Windows 11
- Processor
- Ram
- Nvidia RTX4060ti | Nvidia 4090

## Install


### Visual Studio Community Edition 
[Link](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&channel=Release&version=VS2022&source=VSLandingPage&passive=false&cid=2030)

Click on Individual Components tab and scroll down to Compiler s, build tools, and runtimes.

Tick the boxes starting with C++ ie. (C++ 2022 Redistributable MSMs, C++ 2022 Redistributable Update)

**_Make sure to not tick the boxes of the packages labeled [Deprecated, Out of Support]_**

**Install >  Continue**


### Nvidia Nsight Visual Studio Edition 
[Link](https://developer.nvidia.com/nsight-visual-studio-edition)

*Nvidia Developer Account may be necessary*

Upon installation, Confirm you want the packages to install and press next until you see  Install. Click install.


### Anaconda
[Link](https://www.anaconda.com/download/success)

Run the installer and press Next and Agree to terms of Service.

In **Advanced Installation Option** be sure to have checked 
- Add Anaconda to my PATH Environment variable
- Register Anadconda as my default Python

**Install**



### CUDA Toolkit  12.1
[Link](https://developer.nvidia.com/cuda-12-1-0-download-archive)


***We choose CDUA 12.1 because it is supported by the latest stable version of PyTORCH (2.3.1)


Choose appropriate options for Target Platform to download
- ie. ***Windows, x86_64, Windows 10/11, exe (local)*** 

Run installer > Agree > **Custom(Advanced)** > Make sure that ONLY **CUDA** is ticked. > Next 


### cuDNN
[Link](https://developer.nvidia.com/rdp/cudnn-archive)

*Nvidia Developer Account may be necessary*

Make sure to choose the appropriate version. We are using the Cuda 12.1 So choose the first for CUDA 12.x  

Download Local Installer for Windows(Zip)

Your download should have a name similar to cudnn-windows-x86_64-8.9.7.29_cuda12-archive.zip > *Open* > Click on lib > x64

On your machine: Open Explorer > Local Disk > Program Files > Nvidia GPU Computing Toolkit > CUDA > v12.1 

From the downloaded cuDNN archive go into **x64** and copy the contents inside that folder and transfer them over to the corresponding folder on your machine. Lib > x64

Do the same with files from the **include** and **bin** folders


### Pytorch
[Link](https://pytorch.org/get-started/locally/)

Make sure to choose Appropriately for the system configured. 

Here we are using 
- Stable(2.3.1)
- Windows
- Conda
- Python
- Cuda 12.1

It should give you a command similar to :  conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia

Open up start menu and go to anaconda prompt and input this command to install





## Models
  PYTorch 
 - ForestBuddy-V1
   
## Training 


## FTP Server

## Scripts 
