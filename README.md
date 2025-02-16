# HIGOLA - Linux
HIGOLA Gole2Pro Linux Setup


## Fix for inverted Touchscreen

```
echo $'ENV{LIBINPUT_CALIBRATION_MATRIX}="-1 0 1 0 -1 1"' | sudo tee \
    /etc/udev/rules.d/99-gole2pro-touch.rules
```

## Fix for invertet accelerometer

```
echo $'ENV{ACCEL_MOUNT_MATRIX}="0, -1, 0; -1, 0, 0; 0, 0, 1"' | sudo tee \
    /etc/udev/rules.d/99-gole2pro-accel.rules
```

## Fix for no audio fro Internal Speaker

edit the file     /usr/share/alsa-card-profile/mixer/paths/analog-output-speaker.conf and change this lines: 

```
[Element Headphone]
switch = mute
volume = merge
```
If you on Immutable Distro like Fedora Silverblue, you can copy analog-output-speaker.conf to ~/.config/alsa-card-profile/mixer/paths/analog-output-speaker.conf and edit. 
