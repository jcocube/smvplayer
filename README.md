*The documentation of the project is curently limited. If you are interested in using the sw and experience difficulties or have further questions, please contact Javier Cubelos {jco@gti.ssr.upm.es} and Pablo Carballeira {pablo.carballeira@uam.es} for further information.*

# MV-HMD player
The MV-HMD player is a MultiView (MV) player designed to play MV content (video and static frames) with Head-Mounted Devices (HMD). Additionally, the MV-HMD player can be also used without needing a HMD, simulating the HMD movement using the keyboard.

<img src="images/basics.png" width="400" hspace="20" title="Basics of the MV-HMD player"/> <img src="images/stereo.png" width="400" title="Example of the stereo viewports displayed in the HMD"/> 

## Reference 
Please cite our work: J. Cubelos, P. Carballeira, J. Gutiérrez, N. García, “QoE analysis of Dense Multiview Video with Head-Mounted Devices”, IEEE Transactions on Multimedia, (early access), June 2019.

Link: [https://doi.org/10.1109/TMM.2019.2924575](https://doi.org/10.1109/TMM.2019.2924575)

```
@article{ 
  author={J. {Cubelos} and P. {Carballeira} and J. {Gutiérrez} and N. {García}}, 
  journal={IEEE Transactions on Multimedia}, 
  title={QoE analysis of Dense Multiview Video with Head-Mounted Devices}, 
  year={2019}, 
  volume={}, 
  number={}, 
  pages={1-1}, 
  doi={10.1109/TMM.2019.2924575}, 
  ISSN={1520-9210}, 
  month={},
}
```

## Content

This project contains two main folders: 'build' and 'src'. 'Build' contains a build version of the Unity project ready to run on Windows, while 'src' contains the original Unity Project

## Requirements

* The 'build' folder contains a .exe file with the player ready to run on a Windows platform. 
* The player has been tested:
  - in a computer with the following characteristics: Intel Core i7-4790 CPU 3.60GHz, RAM 32GB, 64bit OS, Windows 10 OS, NVIDIA GeForce GTX970.
  - using the Oculus Rift DK2 headset, but should also run in Oculus CV1.
  - with the support of Oculus Runtime software, that must be installed in the computer
  - and using Unity 3D 2017.3.1f1 software (only needed if you want to modify the source code).

## Build

* The 'SMVPlayer_Data' folder inside this build contains the 'StreamingAssets' folder where the MV videos or frames must be located.
  - The MV videos must be in the 'SMVPlayer_Data/StreamingAssets/videos' path in WEBM's format. All the videos of a same sequence must have the same prefix in the name, followed by a 4 digits number. For example: BBB_Flowers_cam0000,BBB_Flowers_cam0001,...,BBB_Flowers_cam0089,BBB_Flowers_cam0090. 
  - The MV frames must be in the 'SMVPlayer_Data/StreamingAssets/frames' path in PNG's format. All the frames of a same content must have the same prefix in the name, followed by a 4 digits number. For example: frame0_champa0000,frame0_champa0001,...,frame0_champa0078,frame0_champa0079.

## Src

* Additionally, the source code is also provided. It contains two scenes (each one with an associated script) one where the MV content settings must be specified, and the main scene where the playback takes place.
* The project can be easily adapted to run with other HMD headset than Oculus and built to other platforms (Mac, Linux...).

# User manual

## Configuration/Settings screen:
* **Video name format**: Prefix of the video files names common in all the files. For example, for the sequence of 91 videos with videos from BBB_Butterfly_cam0000 to BBB_Butterfly_cam0090, the video name format will be BBB_Butterfly_cam.
* **Number of cameras/videos**: The total number of videos in the sequence.
* **Interocular distance (stereo baseline)**: distance between left and right views (measured in number of camera gaps).
* **Number of background views**: number of views that are played simultaneously in the background, and prepared to be displayed on the screen. 
* **Video resolution**: Resolution of the input videos/frames. We recommend the use of SD resolutions.
* **Switching distance**: horizontal distance between two consecutive views, i.e. distance that the head needs to move to switch to the contiguous view.
* **Type of content**: 1 for MV video, 0 for MV frames.

## KeyMap
* **A**: virtually move the camera to the left
* **D**: virtually move the camera to the right
* **Esc, Enter or C**: go to the player scene
* **M**: increase the light intensity
* **N**: decrese the light intensity
* **S**: force re-synchronization
* **Up**: moving the screens closer to the camera
* **Down**: moving the screens further to the camera


## Notes

* The system is multiplaform but the provided ready-to-run application (build folder) has been built for Windows platform. To run it in other OS, please open the Unity 3D software (src folder) and build it for the desired platform.
* The system should also work for the consumer version CV1 of the Oculus HMD. To use with other HMDs, such as the HTC Vive, please open the Unity scene and change the main camera object.
* After running the application, the Oculus Runtime should automatically starts. If not, please do it manually.
* The MV sequences included in this project were downloaded from:
  - *[1] http://www.fujii.nuee.nagoya-u.ac.jp/multiview-data/*
  - *[2] www.bigbuckbunny.org / P.T. Kovacs, A. Fekete, K. Lackner, V.K. Adhikarla, A. Zare, T. Balogh, “Big Buck Bunny light-field test sequences” provided by Holografika for MPEG FTV AHG, (c) copyright 2008, Blender Foundation*
