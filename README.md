# CAM-IMX327/462/290 Quick Start
![alt text](https://github.com/INNO-MAKER/CAM-MIPI327RAW-and-CAM-MIPI462RAW/blob/main/images/327-426-290.jpg)
- More details please refer to manual
  - [Manual](https://github.com/INNO-MAKER/CAM-MIPI327RAW-and-CAM-MIPI462RAW/blob/main/CAM-IMX290-327-462RAW%20User%20ManualV1.1-EN.pdf)


## Quick Start For Raspberry PI(Not include PI5 and CM5)
- Step1, Open the config.txt on Raspbian:
  - sudo nano /boot/firmware/config.txt
- Step2, Add the following text below the [all] line in the config.txt file
  - dtoverlay=imx290,clock-frequency=74250000
- Step3, change camera_auto_detect=1
  - camera_auto_detect=0
- Step4,reboot and use libcamera for preview
  - sudo reboot
  - libcamera-hello -t 0 

# Quick Start For pi5 or computer module5 

- Step5,downlod json file for imx290/imx426/imx327 sensor module
  - git clone https://github.com/INNO-MAKER/CAM-MIPI327RAW-and-CAM-MIPI462RAW.git
- Step6,use libcamera for preview:
  - libcamera-still -t 0 --tuning-file /home/pi/CAM-MIPI327RAW-and-CAM-MIPI462RAW
/innomakerpi5_imx290.json
