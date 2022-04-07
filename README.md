# rpi-example
Yocto example for raspberrypi3 board

## build instructions

```
git clone --recurse-submodules https://github.com/Halolo/rpi-example.git
cd rpi-example
. init-build-env
bitbake core-image-base
```

The *MACHINE* configured is the raspberrypi3 but you should be able to change it for any machine supported by the meta-raspberrypi layer

## flash

The image target will produce an sdcard image

```
sudo unmount dev/sdX?
sudo dd if=tmp/deploy/images/raspberrypi3/core-image-base-raspberrypi3.rpi-sdimg of=/dev/sdX bs=4M
```

## boot and test

The image contains the openssh deamon

```
ssh root@<IP>
root@raspberrypi3:~# bootgen -h


****** Xilinx Bootgen v2019.2
  **** Build date : Oct 23 2019-04:34:15
    ** Copyright 1986-2019 Xilinx, Inc. All Rights Reserved.
```
