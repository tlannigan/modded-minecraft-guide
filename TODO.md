# TODO

## Higher priority

## Connection to server fails with errors noting identical mod versions

Players will sometimes come to the Discord complaining that they're trying to
connect to a server which they say is running with exactly the same set of mods
as exist on the server side, and they're being disconnected with this error
message:

![Screenshot](https://cdn.discordapp.com/attachments/560188834592063488/1174702001255366787/Direwolf20.png?ex=65688d7e&is=6556187e&hm=34b27ebdcb7ff85fbc1ecae239c6b9156895c3a8a21eafb73ddeae23acce609d&)

This has been blamed on an apparently long-standing bug in Forge (and now of
course NeoForge) in the past, with little further explaination, link to an open
GitHub issue, etc.

In older versions of Forge (1.18.2 at least), this error was much more cryptic
without hinting at the registry factor, so logs would need to be checked to
see if mods are missing (less likely, should result in different error), channel
mismatches, registry mismatches, etc., which might point at the below being true.

One message[1] on the NeoForge Discord server hints at KubeJS scripts which
modify the registry not being in sync, but at least for the Direwolf20 1.20
pack, there are no such registry changes.  Config files not marrying up
(where e.g. the config on one side enables an item and the other disables it)
would also cause registry inconsistencies.

Things to check when this comes up *for FTB packs only*:

  1.  What launcher is being used?

  2.  If the FTB App, recommend install of second instance to rule out bad a
      installation

  3.  If not the FTB App, how was the client-side instance created?

[1] https://discord.com/channels/313125603924639766/437001959950778368/1167862103504334899

## Download attempt failed for: https://dist.modpacks.ch/modpacks/blah

Unless I'm blind, this case isn't covered yet.

What happens is that the app is trying to download e.g.
[this file](https://dist.modpacks.ch/modpacks/1/FTB%20Presents%20Direwolf20%201.20-1.2.0/config/71e8d5d4ffff87d852c3c1dcf2153aaa30c3d0be)
and, for some reason, it can be sometimes be downloaded
fine in a browser, but within the app a 404 is recieved,
leaving the instance install/upgrade in a failed state.

Knowing which SHA1 hash corresponds to a particular
configuration file requires either (a) an awesome memory or (b)
access to the pack.  In the case of this particular URL, the
lazy-yet-inefficient option of downloading file and
`grep(1)`-ing for `aggressiveSpawnChecks = false` confirmed
quickly that the config file in question was
`config/torchmaster.toml`.

This particular instance was worked around with a VPN, so it
seems possible that there's either a common-ish AV/firewall
on (I suspect Windows) that is blocking access to
`dist.modpacks.ch` or there is a transient issue occurring at
Creeperhost causing the download of these pack data files to
fail.

## Basic usage of the FTB mods

A decent fraction of questions in the `#help-and-support` channel
relate to apparently common multiplayer set-ups within FTB Ranks,
and more commonly, how to create and manage quests and configure
custom limits in FTB Quests and FTB Chunks, respectively.

Most common from memory:

  - Where the various FTB mods store their configs

  - Where FTB Quests stores it's data (drafted but probably needs finessing)

  - Common tasks in FTB Quests.  Seem to remember embedding images cropping up
    a fair bit, and less often, how to use the Item Filters mod.

  - Increasing/decreasing claimed and force-loaded chunks in FTB Chunks

  - Configuring different permission levels, chat display aesthetics,
  player labels/prefixes, etc., within FTB Ranks

Less common but does come up on occassion:

  - How to use and configure the FTB Skyblock Companion mod, especially
    the custom recipes required for the hammers

### FTB App UI Screenshots

Text-form documentation is great, but some users are more visual
and capturing/cropping a few screenshots from the FTB App could be
very helpful.

For example, we have instructions guiding users on how to access
e.g. instance logs manually.  While this is more than okay for
the technically able, point-and-click instructions as a
complimentary extra might be an idea.

So, in the case of directing a user to locate a crash report or
`latest.log` for a specific instance within the app, there could
be a screenshot/s showing how to navigate the context menus next
to the green play button of every instance where the `crash-reports`
and `logs` directories can be quickly opened.

### Spotting cracked clients

Checking the first line of a `latest.log` for `--userType, mojang, --versionType` hints at a cracked client.
Check for legitimate usernames on [https://namemc.com/]

## Lower Priority

### Directing users to launcher instance logs/data**

When it comes to directing users to where the FTB App stores its data,
instance files, mod configs, etc., there will possibly be multiple
occurances of *Open File Explorer, navigate to `<PATH>` and then...*.

With this kind of boilerplate in mind, and the desirability of having
instructions for the three OSs the FTB App supports, it should be
relatively simple to script a Python pre-processor[1] to transform the
source of this book, reducing the need for lots of
similiar-yet-slightly-different instructions on files to snag,
pastebins to upload them to, etc.

[1] <https://rust-lang.github.io/mdBook/for_developers/preprocessors.html>

## Debugging Minecraft with VisualVM and other tools

This is an advanced topic and might be overkill, but before I burnt out
last time, I bodged together
[this](https://gist.github.com/ukmcplyr/3b39f568beb191b798aed32be640c5b4)
poor excuse for a tutorial when jikuja was helping users debug an old bug
in the app.

Naturally, it never got finished. And the nice-ish screenshots that
accompanied it now exist only as dead links.  But if another such bug
manifests, it could be worth a dusting off and adding to the book.

<!--
vim: ts=2 sw=2 et fdm=marker :
-->
