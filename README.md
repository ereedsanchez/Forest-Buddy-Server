# Forest-Buddy-Server
Forest Buddy Server 

## Forest Buddy Install 
Prerequisites
- Windows 10 | Windows 11
- Intel/AMD Processors [Has not been tested on the M1 Chipset]
- Nvidia 20 series GPU and above

## Install
Make sure to download the following softwares in the order listed.

### 1. Visual Studio Community Edition 
[Link](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&channel=Release&version=VS2022&source=VSLandingPage&passive=false&cid=2030)

Download should appear in Downloads list. Run file. Click on Individual Components tab and scroll down to Compiler s, build tools, and runtimes.

Scroll down the list and tick *only* the boxes starting with C++ ie. (C++ 2022 Redistributable MSMs, C++ 2022 Redistributable Update)

**_Make sure to not tick the boxes of the packages labeled [Deprecated, Out of Support]_**

**Install >  Continue**


### 2. Nvidia Nsight Visual Studio Edition 
[Link](https://developer.nvidia.com/nsight-visual-studio-edition)

*Nvidia Developer Account may be necessary*

Upon installation, next > Confirm you want the packages to install and press next until you see  Install. Click install.


### 3. Anaconda
[Link](https://www.anaconda.com/download/success)

Run the installer and press Next and be sure to Agree to Terms of Service.

Click Just for Me

#### In **Advanced Installation Option** be sure to have checked 
- Add Anaconda to my PATH Environment variable
- Register Anadconda as my default Python

**Install**



### 4. CUDA Toolkit  12.1
[Link](https://developer.nvidia.com/cuda-12-1-0-download-archive)


***We choose CDUA 12.1 because it is supported by the latest stable version of PyTORCH (2.3.1)


Choose appropriate options for Target Platform to download
- ie. ***Windows, x86_64, Windows 10/11, exe (local)*** 

Run installer > Agree and Continue > **Custom(Advanced)** > Make sure that ONLY **CUDA** is ticked. > Next 


### 5. cuDNN
[Link](https://developer.nvidia.com/rdp/cudnn-archive)

*Nvidia Developer Account may be necessary*

Make sure to choose the appropriate version. We are using the Cuda 12.1 So choose the first for CUDA 12.x  

Download Local Installer for Windows(Zip)

Your download should have a name similar to cudnn-windows-x86_64-8.9.7.29_cuda12-archive.zip > *Open* > Click on lib > x64

On your machine: Open Explorer > Local Disk > Program Files > Nvidia GPU Computing Toolkit > CUDA > v12.1 

From the downloaded cuDNN archive go into **x64** and copy the contents inside that folder and transfer them over to the corresponding folder on your machine. Lib > x64

Do the same with files from the **include** and **bin** folders


### 6. Pytorch
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



#### Verify torch/cuda version

```
python
import torch
torch.__version__
torch.cuda.is_available()
```

### 7. Ultralytics

For good practice, in the name of tidiness, make a directory for each of your projects that contain all its respective files 

I am using yolov8 so i will create a yolov8 virtual environment(venv)

```
conda create -n yolov8 python=3.9
conda activate yolov8
pip install ultralytics
```

```
pip3 install --upgrade torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```


**And to make recheck and sure CUDA is activated for us to use re-enter these commands:



```
python
import torch
torch.__version__
torch.cuda.is_available()
```





## Models
  To get started, navigate to directory created and activate your venv. I decided to make a yolov8 directory in my Users Directory
  
  
  cd C:\Users\XXXXXXXXX\yolov8 

 ```
 conda activate yolov8
 ```


pick detection model for use case:[Link](https://github.com/ultralytics/ultralytics?tab=readme-ov-file)

I will use the **yolov8x.pt model**

```
yolo task=detect mode=predict model=yolov8x.pt source=XXXXXXXXX show=true conf=0.7 line_width=2
```

As you see my model automtically downloads itself to my yolov8 directory upon use.
**Be aware you will recieve an error due to source. so be sure to input a source file to be inferenced.**

Set source=photo.jpg <br> 
Set source=video.mp4 <br> 
Set source= Link to Youtube Video <br>
Set source=0 for Internal Webcam <br> 
Set source=http://CameraSource <br> 
Set source=Directory 

[confidence] conf=0.5 <br>
[show real time] show=true <br>
[save bounding box info] save_txt=true <br>
[save cropped obj] save_crop=true <br>
[hide labels] hide_labels=true<br>
[hide conf] hide_conf=true <br>
line_width=1 <br>


# Some other useful options: <br>

## Predict settings 
source: # (str, optional) source directory for images or videos <br>
vid_stride: 1 # (int) video frame-rate stride <br>
stream_buffer: False # (bool) buffer all streaming frames (True) or return the most recent frame (False) <br>
visualize: False # (bool) visualize model features <br>
augment: False # (bool) apply image augmentation to prediction sources <br>
agnostic_nms: False # (bool) class-agnostic NMS <br>
classes: # (int | list[int], optional) filter results by class, i.e. classes=0, or classes=[0,2,3] <br>
retina_masks: False # (bool) use high-resolution segmentation masks <br>
embed: # (list[int], optional) return feature vectors/embeddings from given layers <br>

## Visualize settings 
show: False # (bool) show predicted images and videos if environment allows <br>
save_frames: False # (bool) save predicted individual video frames <br>
save_txt: False # (bool) save results as .txt file <br>
save_conf: False # (bool) save results with confidence scores <br>
save_crop: False # (bool) save cropped images with results <br>
show_labels: True # (bool) show prediction labels, i.e. 'person' <br>
show_conf: True # (bool) show prediction confidence, i.e. '0.99' <br>
show_boxes: True # (bool) show prediction boxes <br>
line_width: # (int, optional) line width of the bounding boxes. Scaled to image size if None. <br>



### More options can be found [here](https://docs.ultralytics.com/usage/cfg/)   


## Training 


## FTP Server

## Scripts 
