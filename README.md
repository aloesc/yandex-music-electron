# Yandex Music Electron

Desktop application for Yandex Music built with Electron.

---

## Installation from tar.gz

1. Extract the archive to `/opt/yandex-music`:

```bash
sudo mkdir -p /opt/yandex-music
sudo tar -xzf yandex-music-electron-1.0.0.tar.gz -C /opt/yandex-music
```

2. Create a symbolic link for easy launching as `yandex-music`:

```bash
sudo ln -s /opt/yandex-music/yandex-music-electron /usr/local/bin/yandex-music
```

3. Create a desktop entry for menu integration:

```bash
sudo tee /usr/share/applications/yandex-music.desktop > /dev/null <<EOF
[Desktop Entry]
Name=Yandex Music
Exec=/usr/local/bin/yandex-music %U
Icon=/opt/yandex-music/icon.png
Type=Application
Categories=AudioVideo;Player;
StartupNotify=true
StartupWMClass=Yandex Music
EOF
```

---

## Running the app

* To start the app:

```bash
yandex-music
```

* To start minimized to the tray:

```bash
yandex-music --start-minimized
```

---

## Features

* Closing the window hides the app to the system tray instead of quitting.
* Tray menu with options: "Restore" and "Quit".
* Double-clicking the tray icon restores the main window.
* Icon is automatically loaded from multiple possible locations.
* Supports `--start-minimized` flag to launch minimized.

---

## Building

Use the following command to build Linux packages (AppImage, tar.gz, deb, rpm):

```bash
npm run build-linux
```

---

## Requirements

* Linux x64
* Electron 36.3.1
* Dependencies for packages: `gtk3`, `libnotify`, `nss`, `libXScrnSaver`, `xdg-utils`, `at-spi2-core`, etc.

---

Thank you for using the app!

