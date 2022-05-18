## 依赖

```bash
yay mpv xwinwrap
```

## 安装

```bash
tee ~/.local/share/applications/wallpaper.desktop << EOF
[Desktop Entry]
Name=MPV WallPaper
Exec=bash -c 'killall xwinwrap; sleep 1; xwinwrap -fs -fdt -ni -b -nf -un -- mpv -wid WID --stop-screensaver=no --hwdec=auto --hwdec-codecs=all --no-audio --no-osc --no-osd-bar --no-input-default-bindings --loop-file /home/cong/Videos/wall.mp4' &
Icon=desktop
Type=Application
#FIX: DoesNot ShowUp In Compiz Session
#OnlyShowIn=XFCE;GNOME;
#NotShowIn=KDE;
EOF
```

## 开机自启动

```bash
ln -sf ~/.local/share/applications/wallpaper.desktop ~/.config/autostart/
```


## 退出

```bash
killall xwinwrap
```