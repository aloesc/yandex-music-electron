# Yandex Music Electron

A lightweight desktop application for Yandex Music built with Electron, providing a seamless music streaming experience with system tray integration and cross-platform support.

## Table of Contents

- [Installation](#installation)
- [Running the App](#running-the-app)
- [Features](#features)
- [Building](#building)
- [Supported Platforms](#supported-platforms)
- [Requirements](#requirements)
- [License](#license)
- [Contributing](#contributing)

## Installation

To install the application from a `tar.gz` archive on Linux, follow these steps:

1. **Extract the archive** to `/opt/yandex-music`:

   ```bash
   sudo mkdir -p /opt/yandex-music
   sudo tar -xzf yandex-music-electron-1.0.0.tar.gz -C /opt/yandex-music
   ```

2. **Create a wrapper script** for proper launching:

   ```bash
   sudo tee /usr/local/bin/yandex-music > /dev/null <<EOF
   #!/bin/bash
   cd /opt/yandex-music
   exec ./yandex-music-electron "$@"
   EOF

   sudo chmod +x /usr/local/bin/yandex-music
   ```

3. **Create a desktop entry** for menu integration:

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

## Running the App

- **Start the app** normally:

  ```bash
  yandex-music
  ```

- **Start minimized** to the system tray:

  ```bash
  yandex-music --start-minimized
  ```

## Features

- **System Tray Integration**: Closing the window minimizes the app to the system tray instead of quitting.
- **Tray Menu**: Includes "Restore" and "Quit" options.
- **Double-Click Restore**: Double-click the tray icon to restore the main window.
- **Flexible Icon Loading**: Automatically loads the app icon from multiple possible locations.
- **Minimized Start**: Supports the `--start-minimized` flag for launching directly to the tray.

## Building

To build the application for Linux (AppImage, tar.gz, deb, rpm), run:

```bash
npm run build-linux
```

## Supported Platforms

- **Linux (x64)**: AppImage, tar.gz, deb, rpm packages
- **Windows**: NSIS installer
- **macOS**: DMG installer

## Requirements

- **Operating System**: Linux x64, Windows, or macOS
- **Electron**: Version 36.3.1
- **Linux Dependencies**: `gtk3`, `libnotify`, `nss`, `libXScrnSaver`, `xdg-utils`, `at-spi2-core`, etc.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an issue on the [GitHub repository](https://github.com/your-repo/yandex-music-electron).

---

Thank you for using Yandex Music Electron!