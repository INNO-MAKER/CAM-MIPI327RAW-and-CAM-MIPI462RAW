## CAM-IMX462RAW  Quick Start:

This document is to guide you on how to quickly test this camera on the Raspberry Pi 5. If you don't have experience with Raspberry Pi or its cameras, or if you need more information, please refer to the user manual.

The CAM-IMX462RAW can be used with the Raspberry Pi system's built-in drivers and the libcamera/rpicam tools. It can be used directly once the DTOVERLAY configuration is completed

### 1. Dtoverlay

1.Open  the config.txt on terminal via build-in nano tools.

```
sudo nano /boot/firmware/config.txt
```

Legacy version system：

```
sudo nano /boot/config.txt
```

2.Append the following lines to the end of the files.

camera 1 (default):   

```
dtoverlay=imx290,clock-frequency=74250000,cam1
```

camera 0 (default):   
```
dtoverlay=imx290,clock-frequency=74250000,cam0
```
3.Pressing CTRL+ x key to exit and pressing  y’ key to save your changes. Finally, reboot.

```
sudo reboot
```

### 2. Camera Information

```
rpicam-hello --list-cameras
```

### 3. Camera Preview

For camera 0: 

```
rpicam-hello -t 0 --camera 0
```

For camera 1:

```
rpicam-hello -t 0 --camera 1
```

### 4. Camera Mode Setting

The CAM-MIPIOV9281 V2 supports the following operating modes under the built-in drivers of the Raspberry Pi.

RAW10 :  1280x720@60 fps

​                 1920x1080@60 fps

RAW12: 1280x720@60 fps

​               1920x1080@60 fps

Below, I will provide two examples to demonstrate how to set the operating modes.

(1) Set the working mode of camera 1 to 1920x1080,RAW12 and 60 frame rate using the following command

```
rpicam-still --viewfinder-mode 1920:1080:12 --framerate 60 -t 0 --camera 1
```

(2) Set the working mode of camera 0 to 1280x800, RAW10, and 114 frame rate using the following command

```
rpicam-still --viewfinder-mode 1280:720:10 --framerate 60 -t 0 --camera 0
```



​                                                                                                                                                                                            Author : Calvin （calvin@inno-maker.com）

​                                                                                                                                                                                           Support: support@inno-maker.com
