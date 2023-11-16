# FTB App common issues

-----

Solutions for common issues that can occur during the use of the FTB App.

## FTB-AUTH Errors

| Code   | Error                                                           | Solution                                                                                                                                                                                                                       |
|--------|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 000001 | Failed to authenticate with Xbox Live                           | Microsoft/Xbox issue.                                                                                                                                                                                                          |
| 000002 | Failed to authenticate with Xbox Secure Token Service (XSTS)    | Microsoft/Xbox issue.                                                                                                                                                                                                          |
| 000003 | Failed to login with Xbox                                       | Microsoft/Xbox issue.                                                                                                                                                                                                          |
| 000004 | Failed to check games owned by account                          | Microsoft/Xbox issue.                                                                                                                                                                                                          |
| 000005 | Failed to find user's Minecraft profile                         | Launch `Minecraft: Java Edition` in the vanilla launcher at least once.                                                                                                                                                        |
| 000006 | Account does not own Minecraft                                  | Verify you are logging in with the right Microsoft account. If the account absolutely owns Minecraft, try deleting `profiles.json` file in the [FTB App directory](launcher_ftb-app.md#find-the-default-directory-by-either).  |
| 000012 | Account does not have an Xbox Live account                      | Microsoft set a deadline of Sept. 19th, 2023 for all Mojang accounts to migrate to Microsoft accounts. If you didn't migrate you no longer own Minecraft.                                                                      |
| 000013 | Account is from a region that does not support Xbox Live        | Create an Xbox account in a region supported by Xbox Live.                                                                                                                                                                     |
| 000014 | Account needs adult verification from Xbox                      | Have an adult in your Xbox Family allow your access.                                                                                                                                                                           |
| 000015 | Account is under 18                                             | You must be 18 or have adult consent to use the FTB App.                                                                                                                                                                       |
| 000016 | Other error logging into Xbox                                   | Unknown error.                                                                                                                                                                                                                 |

## The FTB App says I don't own Minecraft

-----

Make sure you own Minecraft on a Microsoft account. If you bought Minecraft when it was still using Mojang accounts, there was a deadline on Sept. 19th, 2023 to migrate to a Microsoft account. If you did not migrate, you do not own Minecraft anymore and will be unable to login with your Mojang credentials. Microsoft did send out a mercy email on that day which will allow anyone that didn't meet the deadline to get a new Minecraft account attached to their Microsoft account, up to 90 days from the deadline.

## An error occurred whilst launching... Failed to execute asset update task

-----

Check your FTB App's `latest.log` for lines that say:

`Tried URL: https://resources.download.minecraft.com/blah/blahblahblah...`

Take note specifically of the `/blah/blahblahblah` part. It is a vanilla Minecraft file that the launcher requires:

1. In your File Explorer navigate to `C:/Users/<your_username>/AppData/Local/.ftba/bin/assets/objects` and find the folder with the first `blah` in your URL (if your URL ended in  `/e8/e8fddnjabdsf` find the `e8` folder and then the file called `e8fddnjabdsf`).

2. Delete this file and relaunch your FTB App.

## Trying to sign in through Microsoft is giving me "We can't find the FTB App"

-----

If you are on a Mac use a browser other than Safari to log in with. When you login you can copy the URL at the top and paste it into another browser of your choice.

## Haven't found your issue?

-----

Take a look at the [general modded Minecraft errors](./common-issues.md) that are not specific to the FTB App.
