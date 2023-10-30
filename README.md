# Modded Minecraft Help

- This documentation is for users and server operators experiencing issues with modded Minecraft, including singleplayer worlds, servers, and various third-party Minecraft launchers.

# General Modded Minecraft

## Logs

- The easiest way to get help debugging your issue is usually by sharing your game logs with others. Best practice when providing logs is to fully close Minecraft and your launcher, relaunch your game and make it crash again, then provide your logs to others. This makes tracking your issue or crash easier as the log file is much smaller.

- There are three common types of logs used to help debug issues:
  - Minecraft game logs that can usually be found under `logs` in your modpack folder. These are *usually* named `latest.log` or `debug.log` (if you have file extensions disabled they will appear as `latest` and `debug` in your folder).
  - Crash reports that can usually be found under `crash-reports` in your modpack folder. These are *usually* named `crash-DATETIME-client.txt` or `crash-DATETIME-server.txt`.
  - Java Runtime crashes that can usually be found in the root of your modpack folder. These are *usually* named `hs_err_pid###.log`.

- Logs can be provided as-is in their original file format, or they can be uploaded to a website such as https://mclo.gs to strip any identifying information and make debugging easier for those helping you. Copy the URL to share it with others.

## Common Issues

### My server is really laggy!
  - Open a ticket with your server's hosting provider if they offer support. They have access to your server directly and can find the culprit more easily.
  - A common source of consistent lag can be caused by chunk generation when players are exploring the world and creating new chunks. Install the Chunk Pregenerator mod and run this command:
	- `/pregen start gen radius <a_name_for_the_task> CIRCLE 0 0 <chunk_radius_to_pregenerate>`
	- Remember that chunks are 16 blocks wide, so setting the chunk radius to 100 will generate chunks out to 1600 blocks from spawn (100 x 16) in all directions. Start with a number like 100 and then build from there. The bigger the radius you choose the longer it will take, some radiuses may take hours. This is normal, and you should run this when your players are offline for the best performance.
  - Many modern modpacks come with the Spark mod pre-installed (and if not, install it in your server's `mods` folder). Load into your server and follow these steps (note these commands are different than the singleplayer commands):
	- Run `/spark profile start`
	- Play the game for a minute
	- Run `/spark profile stop`

### My singleplayer world is really laggy!
  - Is your hardware good enough to run the modpack? Large modpacks can be intensive on an underpowered computer.
	- Most modpacks require you to allocate between 4-8GB of memory (RAM). If your system only has 8GB or less you may be running into issues.
	- Make sure you have a discrete GPU (such as Nvidia or AMD) to have the best experience playing modded Minecraft. If you don't you may run into issues, especially playing on larger modpacks.
  - Many modern modpacks come with the Spark mod pre-installed (and if not, install it in your modpack's `mods` folder). Load into your world and follow these steps (note that these commands are different than the server commands):
	- Run `/sparkc profile start`
	- Play the game for a minute
	- Run `/sparkc profile stop`

# FTB App (Minecraft launcher)

- This section is for those using the FTB App and references specific file paths that the program defaults to.

## Logs

### How to provide your logs

- Logs can be provided in one of two ways:
  - FTB distributes a debugging tool to share your logs to others, called the `FTB Debug` tool. This tool is available for several operating systems and architectures:
    - [Windows](https://dist.creeper.host/tools/ftb-debug/ftb-debug.exe)
    - [Windows (Arm)](https://dist.creeper.host/tools/ftb-debug/ftb-debug-arm64.exe)
    - [MacOS](https://dist.creeper.host/tools/ftb-debug/ftb-debug-macos)
    - [MacOS (Arm/M1/M2)](https://dist.creeper.host/tools/ftb-debug/ftb-debug-macos-arm64)
    - [Linux](https://dist.creeper.host/tools/ftb-debug/ftb-debug-linux)
    - [Linux (Arm)](https://dist.creeper.host/tools/ftb-debug/ftb-debug-linux-arm)

	- [FTB Debug tool instructions](https://go.ftb.team/ftbdbg-support)

  - Manually providing your logs [referenced in the next section](#which-logs-should-i-send)

### Which logs should I send?
  - My server is having issues:
    - For server logs, you'll have to know where you put your server's folder, or find it on your hosting provider's control panel or FTP (depending on your host).
	- Reference the [general logs section](#logs) and provide your `latest.log` and any crash reports that were created at the time the server crashed.

  - My game client is having issues:
    - FTB modpack folders on Windows systems are stored by default in `C:/Users/<your_username>/AppData/Local/.ftba/instances/<your_instance_ID>`
    - Reference the [general logs section](#logs) and provide your `latest.log`, any crash reports that were created at the time you crashed, and look for any Java runtime crashes.

  - My FTB App is having issues:
    - FTB App folders on Windows systems are stored by default in `C:/Users/<your_username>/AppData/Local/.ftba`
	- In your FTB App's folder look for a folder called `logs`, open it and find a file called `latest.log` (or just `latest` if you have file extensions disabled).

  - Logs can be provided as-is in their original file format, or they can be uploaded to a website such as https://mclo.gs to strip any identifying information and make debugging easier for those helping you. Copy the URL to share it with others.


## Common Issues:

### My FTB App opens a popup with errors!
  - The FTB App says I don't own Minecraft!
    - Make sure you own Minecraft on a Microsoft account. If you bought Minecraft when it was still using Mojang accounts, there was a deadline on Sept. 19th, 2023 to migrate to a Microsoft account. If you did not migrate, you do not own Minecraft anymore and will be unable to login with your Mojang credentials. Microsoft did send out a mercy email on that day which will allow anyone that didn't meet the deadline to get a new Minecraft account attached to their Microsoft account, up to 90 days from the deadline.

### An error occurred whilst launching... Failed to execute asset update task:
  - Check your FTB App's `latest.log` for lines that say `Tried URL: https://resources.download.minecraft.com/blah/blahblahblah...`. Take note specifically of the `/blah/blahblahblah` part. If only one `/blah/blahblahblah` is referenced in your log, you can replace it in your install. It is a vanilla Minecraft file that the launcher requires:
    - Go to your specific `https://resources.download.minecraft.com/blah/blahblahblah` URL in your browser. 
	- If using a Chromium browser (Chrome, Edge, Brave, etc) hover over the file player in the middle of the screen and click the 3 dots and download the file.
	- In your File Explorer navigate to `C:/Users/<your_username>/AppData/Local/.ftba/bin/assets/objects` and find the folder with the first `blah` in your URL (if your URL ended in `/e8/e8fddnjabdsf` find the `e8` folder).
	- Copy the downloaded file into this directory and relaunch your FTB App.

### My game crashed and I have a file called `hs_err_pidXXXX.log` in my modpack folder now!
  - Open the log with any text editor. Check for the mention of `atio6axx.dll` under `Problematic frame:`, if you find it it means there's a problem with an AMD driver on your computer.
    - If you use an AMD video card, you need to update drivers for it.
    - If you don't have an AMD video card but have an AMD CPU, your computer may be using your integrated GPU instead of your dedicated GPU. Make sure your monitor is plugged into your GPU and not your motherboard. If that's not the issue, Google "Nvidia changing preferred GPU".

### Trying to sign in through Microsoft is giving me "We can't find the FTB App"!
  - If you are on a Mac use a browser other than Safari to log in with. When you login you can copy the URL at the top and paste it into another browser of your choice.

### Screen turns black when holding items
  - Using integrated graphics (iGPU) seems to cause this issue with older versions of Minecraft, most commonly on version 1.7. You can try updating your iGPU drivers or install a discrete GPU into your computer.

