# Modded Minecraft Guide

- This documentation is for users and server operators experiencing issues with modded Minecraft, including singleplayer worlds, servers, and various third-party Minecraft launchers.

# General Modded Minecraft

## Logs

- The easiest way to get help debugging your issue is usually by sharing your game logs with others. Best practice when providing logs is to fully close Minecraft and your launcher, relaunch your game and make it crash again, then provide your logs to others. This makes tracking your issue or crash easier as the log file is much smaller.

- There are three common types of logs used to help debug issues:
  - Minecraft game logs that can usually be found under `logs` in your modpack folder. These are *usually* named `latest.log` or `debug.log` (if you have file extensions disabled they will appear as `latest` and `debug` in your folder).
  - Crash reports that can usually be found under `crash-reports` in your modpack folder. These are *usually* named `crash-DATETIME-client.txt` or `crash-DATETIME-server.txt`.
  - Java Runtime crashes that can usually be found in the root of your modpack folder. These are *usually* named `hs_err_pid###.log`.

- Logs can be provided as-is in their original file format.