# SVXrptr HAT (https://rf.guru)

The drivers of [WM8960 Audio CHIP] for Raspberry Pi.
The GPIO pinouts for driving (and reading) a repeater.

### Update everything
```bash
sudo apt -y update
sudo apt -y upgrade
sudo reboot
```

### Modify boot config (/boot/config.txt)
Search for dtoverlay=vc4-kms-v3d and add ,noaudio to the line
```bash
dtoverlay=vc4-kms-v3d,noaudio
```

### Install wm8960-soundcard
Get the wm8960 soundcard source code. and install all linux kernel drivers

```bash
cd WM8960-Audio-HAT
sudo ./install.sh 
sudo reboot
```

Check that the sound card name matches the source code wm8960-soundcard.

```bash
$ aplay -l
```

### GPIO Pins
Description of the GPIO pins
```text
GPIO 7 -> output ... Drive High for disabling the audio bypass (audio is in bypass by default)
GPIO 16 -> output ... Drive PTT (for any type of PTT (relay)
GPIO 12 -> input ... depending on your tranceiver ... logic voltage can be between 3.3v and 24v
```


