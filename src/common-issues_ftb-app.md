# FTB App common issues

-----

Solutions for common issues that can occur during the use of the FTB App.

## FTB-AUTH Errors

| Code   | Error                                                                       | Solution                                                                                                                                                                                                                       |
|--------|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 000001 | Failed to authenticate with Xbox Live                                       | Microsoft/Xbox issue.                                                                                                                                                                                                          |
| 000002 | Failed to authenticate with Xbox Secure Token Service (XSTS)                | Microsoft/Xbox issue.                                                                                                                                                                                                          |
| 000003 | Failed to login with Xbox                                                   | Microsoft/Xbox issue.                                                                                                                                                                                                          |
| 000004 | Unable to verify account entitlements                                       | You've likely logged in with the wrong account.                                                                                                                                                                                |
| 000005 | Failed to find user's Minecraft profile                                     | Launch `Minecraft: Java Edition` in the vanilla launcher at least once.                                                                                                                                                        |
| 000006 | Account does not own Minecraft                                              | Verify you are logging in with the right Microsoft account. If the account absolutely owns Minecraft, try deleting `profiles.json` file in the [FTB App folder](launcher_ftb-app.md#how-to-find-the-default-folder).  |
| 000012 | Account does not have an Xbox Live account                                  | Microsoft set a deadline of Sept. 19th, 2023 for all Mojang accounts to migrate to Microsoft accounts. If you didn't migrate you no longer own Minecraft.                                                                      |
| 000013 | Account is from a region that does not support Xbox Live                    | Create an Xbox account in a region supported by Xbox Live.                                                                                                                                                                     |
| 000014 | Account needs adult verification from Xbox                                  | Have an adult in your Xbox Family allow your access.                                                                                                                                                                           |
| 000015 | Account is under 18                                                         | You must be 18 or have adult consent to use the FTB App.                                                                                                                                                                       |
| 000016 | Account has been rejected by Xbox Live services for an unknown reason       | Unknown error.                                                                                                                                                                                                                 |

## The FTB App says I don't own Minecraft

-----

Make sure you own Minecraft on a Microsoft account. If you bought Minecraft when it was still using Mojang accounts, there was a deadline on Sept. 19th, 2023 to migrate to a Microsoft account. If you did not migrate, you do not own Minecraft anymore and will be unable to login with your Mojang credentials. Microsoft did send out a mercy email on that day which will allow anyone that didn't meet the deadline to get a new Minecraft account attached to their Microsoft account, up to 90 days from the deadline.

## An error occurred whilst launching... Failed to execute asset update task

-----

Check the `latest.log` file in the [FTB App folder](launcher_ftb-app.md#my-ftb-app-is-having-issues) for lines that say:

`Tried URL: https://resources.download.minecraft.com/blah/blahblahblah...`

Take note specifically of the `/blah/blahblahblah` part. It is a vanilla Minecraft file that the launcher requires:

1. In File Explorer navigate to `C:/Users/<your_username>/AppData/Local/.ftba/bin/assets/objects` and find the folder with the first `blah` in the URL (if the URL ended in  `/e8/e8fddnjabdsf` find the `e8` folder and then the file called `e8fddnjabdsf`).

2. Delete this file and relaunch the FTB App.

## Trying to sign in through Microsoft is giving me "We can't find the FTB App"

-----

Using Brave or Safari browsers often cause issues signing into the FTB App. Try disabling Brave Shield or use a different browser. Copy the URL at the top and paste it into another browser of your choice.

## Caused by: java.security.cert.CertificateNotYetValidException in `debug.log`

-----

Your computer's date and time are set incorrectly. Allow Windows to set it [automatically](https://support.microsoft.com/en-us/windows/how-to-set-your-time-and-time-zone-dfaa7122-479f-5b98-2a7b-fa0b6e01b261) for you.

## Haven't found your issue?

-----

Take a look at the [general modded Minecraft errors](common-issues.md) that are not specific to the FTB App.
