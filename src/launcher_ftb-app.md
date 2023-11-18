# FTB App

-----

The FTB App is the first-party software for installing FTB modpacks, ensuring the FTB modpacks you download are in their intended form and have the most up-to-date versions available. The FTB App also supports CurseForge modpacks, and downloads CurseForge mods using the CurseForge API to support mod developers.

## Files and folders

-----

### How to find the default directory

- #### Windows
    - Press `Windows + R` and type `%localappdata%/.ftba`.
- #### MacOS
    - Open a new Terminal and type `open ~/Library/Application\ Support/.ftba`.
- #### Linux
    - Navigate to the `~/.ftba` directory.

### Directory contents

- `/.doh_cache` - Folder for DNS over HTTPS, containing DNS communication information

- `/bin`
    - `/assets` - Minecraft assets
    - `/libraries` - launcher related files
    - `/runtime` - Java binaries
    - `/versions` - Forge jars

- `/instances` - Folders for each modpack you have installed

- `/logs`
    - `debug.log` - Verbose logs that were recorded while the FTB App was last open
    - `latest.log` - Logs that were recorded while the FTB App was last open
    
- `/storage` - Stores a JSON file with version information
- `profiles.json` - Stores profile information for Minecraft and Xbox, including tokens
- `subprocess.pid` - Stores a process ID

### Modpack folders

- Found on the modpack's page in the FTB App, clicking `Settings`, and clicking `Open Folder` at the bottom.

## Providing logs

-----

Logs can be provided in one of two ways:

1. Manually providing your logs [found in the next section](#which-logs-should-i-send).

2. Using a tool FTB distributes to share your logs to others called the `FTB Debug` tool. This tool has [instructions](https://go.ftb.team/ftbdbg-support) and is available for several operating systems and architectures:

    - [Windows](https://dist.creeper.host/tools/ftb-debug/ftb-debug.exe)

    - [Windows (Arm)](https://dist.creeper.host/tools/ftb-debug/ftb-debug-arm64.exe)

    - [MacOS](https://dist.creeper.host/tools/ftb-debug/ftb-debug-macos)

    - [MacOS (Arm/M1/M2)](https://dist.creeper.host/tools/ftb-debug/ftb-debug-macos-arm64)

    - [Linux](https://dist.creeper.host/tools/ftb-debug/ftb-debug-linux)

    - [Linux (Arm)](https://dist.creeper.host/tools/ftb-debug/ftb-debug-linux-arm)

## Which logs should I send?

-----

### My server is having issues:

- For server logs, you'll have to know where you put your server's folder, or find it on your hosting provider's control panel or FTP (depending on your host).

- Reference the [general logs section](debugging.md#logs) and provide your `latest.log` and any crash reports that were created at the time the server crashed.

### My Minecraft client is having issues:

- FTB modpack folders can be found by opening the modpack's page in the FTB App, clicking `Settings` on the right, then click `Open Folder` at the bottom.

- Reference the [general logs section](debugging.md#logs) and provide your `latest.log`, any crash reports that were created at the time you crashed, and look for any Java runtime crashes.

### My FTB App is having issues:

- In your [FTB App's folder](#how-to-find-the-default-directory) look for a folder called `logs`, open it and find a file called `latest.log` (or just `latest` if you have file extensions disabled).

Logs can be provided as-is in their original file format.
