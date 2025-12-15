# Xwinwrap

Fork Of xwinwrap.  
Xwinwrap Allows You To Stick An App Such As A Video Player, Gif, Or Webp Viewer To Your Desktop Background.

### Installing Dev Dependency

```
sudo apt install xorg-dev build-essential libx11-dev x11proto-xext-dev libxrender-dev libxext-dev gifsicle libwebp-dev
git clone https://github.com/zackshdw/xwinwrap.git
cd xwinwrap
make
sudo make install
make clean
```

### Uninstalling

```
cd /path/to/xwinwrap
sudo make uninstall
cd ..
rm -r xwinwrap
```

### Usage

```
Usage:
    xwinwrap [OPTIONS...] -- <video-player> [VIDEO-PLAYER OPTIONS...] <video-file>

Options:
             -g {w}x{h}+{x}+{y}
                     - Specify Geometry (w=width, h=height, x=x-coord,
                       y=y-coord. Ex: -g 640x480+100+100)
             -ni     - Ignore Input
             -argb   - RGB
             -fdt    - Force WID Window A Desktop Type Window
             -fs     - Full Screen
             -un     - Undecorated
             -s      - Sticky
             -st     - Skip Taskbar
             -sp     - Skip Pager
             -a      - Above
             -b      - Below
             -nf     - No Focus
             -o      - Opacity Value Between 0 to 1 (Ex: -o 0.20)
             -sh     - Shape Of Window (Choose Between Rectangle, Circle Or
                       Triangle. Default Is Rectangle)
             -ov     - Set override_redirect Flag (For Seamless Desktop
                       Background Integration In non-fullscreenmode) (Can Cause
                       Artifacts On Some Environments)
             -ovr    - Set override_redirect Flag On root Window (For Seamless
                       Desktop Background Integration In fullscreenmode)
             -d      - Daemonize
             -debug  - Enable Debug Messages
```

Example

```bash
xwinwrap -ov -g 1366x768+0+0 -- gifview -w WID mygif.gif -a
```

```bash
xwinwrap -ov -g 1366x768+0+0 -- \
  mpv -wid WID \
      --no-config \
      --keepaspect=yes \
      --loop \
      --no-border \
      --no-osc \
      --no-osd-bar \
      --no-input-default-bindings \
      --input-vo-keyboard=no \
      --vo=gpu \
      --profile=low-latency \
      --no-audio \
      --hwdec=auto \
      /path/video/or/webp
```

---

Original Source - https://launchpad.net/xwinwrap
