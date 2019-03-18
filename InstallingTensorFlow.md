
Notes on my attempt to install TensorFlow

Inte Xeon CPU E5-2643 v4 @ 3.4 GHz (two)
64 GM RAM

Windows10 Enterprise version 1803, build 17134.590

NVidia GeForce 1080 graphics cards with GPU (three)

Updated Nvidia graphics driver to 419.35 (driver only, express installation option...not custom)

Used admin privs to instal Nvidia CUDA toolkit 10.1.105_418.96_win10.exe from here https://developer.nvidia.com/cuda-downloads?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exelocal. At first, I did not see any evidence that CUPTI was installed, but it looks like everything needed is in the extras directory. 

Following instructions here: https://developer.nvidia.com/rdp/cudnn-download. Downloaded the cuDNN libraries as `cudnn-10.1-windows10-x64-v7.5.0.56.zip`, and put the zip file in `C:\Program Files\NVIDIA GPU Computing Toolkit`. This required admin privleges.

Following instructions at https://www.tensorflow.org/install/gpu, I set the paths for
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\extras\CUPTI\libx64

I did not know what this referred to, and did not set it:
C:\tools\cuda\bin

Downloaded CUPTI cupti-win64-2019.1.1.1.zip from https://developer.nvidia.com/gameworksdownload#?dn=cuda-profiler-tools-interface-cupti-2019-1 and put the zip file in the same directory. Turns out this was unessecary...the libraries appeard in 

Per https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/

C:\Users\csherwood>nvcc -V
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2019 NVIDIA Corporation
Built on Fri_Feb__8_19:08:26_Pacific_Standard_Time_2019
Cuda compilation tools, release 10.1, V10.1.105
