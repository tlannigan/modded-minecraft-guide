# Common issues

## My server is lagging

-----

Open a ticket with your server's hosting provider if they offer support. They have access to your server directly and can find the culprit more easily.

A common source of consistent lag can be caused by chunk generation when players are exploring the world and creating new chunks. Install the Chunk Pregenerator mod and run this command:

- `/pregen start gen radius <any_name_for_the_task> CIRCLE 0 0 <chunk_radius_to_pregenerate>`

- Remember that chunks are 16 blocks wide, so setting the chunk radius to 100 will generate chunks out to 1600 blocks from spawn (100 x 16) in all directions. Start with a number like 100 and then build from there. The bigger the radius you choose the longer it will take, some radiuses may take hours. This is normal, and you should run this when your players are offline for the best performance.

Many modern modpacks come with the Spark mod pre-installed (and if not, install it in your server's `mods` folder). Load into your server and follow these steps (note these commands are different than the singleplayer commands):

- Run `/spark profiler start`

- Play the game for a minute

- Run `/spark profiler stop`

## My singleplayer world is lagging

-----

Is your hardware good enough to run the modpack? Large modpacks can be intensive on an underpowered computer.

- Most modpacks require you to allocate between 4-8GB of memory (RAM). If your system only has 8GB or less you may be running into issues.

- Make sure you have a discrete GPU (such as Nvidia or AMD) to have the best experience playing modded Minecraft. If you don't you may run into issues, especially playing on larger modpacks.

Many modern modpacks come with the Spark mod pre-installed (and if not, install it in your modpack's `mods` folder). Load into your world and follow these steps (note that these commands are different than the server commands):

- Run `/sparkc profiler start`

- Play the game for a minute

- Run `/sparkc profiler stop`

## My game crashed and I have a file called `hs_err_pidXXXX.log` in my modpack folder now

-----

Open the log with any text editor. Check for the mention of `atio6axx.dll` under `Problematic frame:`, if you find it it means there's a problem with an AMD driver on your computer.

- If you use an AMD video card, you need to update drivers for it.

- If you don't have an AMD video card but have an AMD CPU, your computer may be using your integrated GPU instead of your dedicated GPU. Make sure your monitor is plugged into your GPU and not your motherboard. If that's not the issue, Google "Nvidia changing preferred GPU".

## Screen turns black when holding items

-----

Using integrated graphics (iGPU) seems to cause this issue with older versions of Minecraft, most commonly on version 1.7. You can try updating your iGPU drivers or installing a discrete GPU into your computer.
