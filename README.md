
# Yandex Music Electron

Desktop application for Yandex Music built with Electron.

---

## Installation from tar.gz (Linux)

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

## Installation on Windows

1. Download the installer `.exe` from the release page.
2. Run the installer and follow the instructions.
3. The app will be available in the Start Menu as **Yandex Music**.

---

## Installation on macOS

1. Download the `.dmg` file from the release page.
2. Open the `.dmg` and drag the **Yandex Music** app to the Applications folder.
3. Launch the app from Applications or Spotlight.

---

## Running the app

* Linux:

```bash
yandex-music
```

* Windows and macOS:

- Launch from Start Menu (Windows) or Applications (macOS).

* To start minimized to the tray (Linux only):

```bash
yandex-music --start-minimized
```

---

## Features

* Closing the window hides the app to the system tray instead of quitting.
* Tray menu with options: "Restore" and "Quit".
* Double-clicking the tray icon restores the main window.
* Icon is automatically loaded from multiple possible locations.
* Supports `--start-minimized` flag to launch minimized (Linux).
* Native installers for Windows and macOS.

---

## Building

Use the following command to build Linux packages (AppImage, tar.gz, deb, rpm):

```bash
npm run build-linux
```

For Windows:

```bash
npm run build -- --win
```

For macOS:

```bash
npm run build -- --mac
```

For all platforms:

```bash
npm run build-all
```

---

## Requirements

* Linux x64, Windows x64, macOS (Intel/Apple Silicon support depends on Electron version)
* Electron 28+
* Linux dependencies: `gtk3`, `libnotify`, `nss`, `libXScrnSaver`, `xdg-utils`, `at-spi2-core`, etc.

---

Thank you for using the app!