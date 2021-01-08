---
title: "Moving from SX to Atmosphere"
permalink: migrate_eng
---

{% spoiler Why switch to Atmosphere? %}

In October 2020 [two Xecuter Team leaders were arrested](https://www.theverge.com/2020/10/2/21499297/team-xecuter-selling-nintendo-hacks-arrested-charged-fraud){: target = "_ blank"} - a campaign engaged in the development and support of SXOS, as well as the production of chips for modifying set-top boxes with a closed vulnerability.

On December 1, 2020, the Switch system software update under version 11.0.0 is released and after 5 days the SXOS team released a firmware supporting this update. Everything seems to be going well and despite the arrests, the XTs are still working.

However, at about the same time, all Chinese sites that sold chips unanimously began to say that they had run out of chips and the prospects for the production of new batches were very dim. Rumors also began to spread that all chip manufacturing factories were closed and products had been confiscated. The staff was dispersed, and the ban on the sale of chips was launched from almost the top of the Chinese Communist Party. Which is not so hard to believe if you remember that the most powerful corporation Tencent is the official distributor of Nintendo products in China.

The last straw confirming that evil tongues are probably right was the release of firmware 11.0.1, which at the time of this writing is still not working on SXOS.

It should be noted that the 11.0.1 update was minor and Atmosphere was already working with it by the evening of the same day.

At the beginning of 2021, Atmosphere 0.17.0 was released, which already fully supported work on chip set-top boxes, so now you don't have to wait for new versions of SXOS - it's just no longer necessary.

{% endspoiler %}

## Moving from SX to Atmosphere

Choose the option that suits you and follow the instructions.

{% spoiler Fusée Gelée flashing attachment or Caffeine flashing %}

1. Insert the memory card of the set-top box into the PC
1. Install {% include abbr/kefir_addr.txt %} by choosing "**Atmosphere**" as an option (`atmo.zip` for manual installation)
1. Wait for the installation to complete, then return the memory card to the console
1. Turn on the console
1. If you had EmuNAND, on the kefir screensaver**press the volume down button**to get into hekate
1. Go to "**emuMMC**"
1. Click "**Migrate emuMMC**"
1. Select "**Emunand**" -> "**Continue**"
1. After finishing the migration, click "**Change emuMMC**" and on the right side of the screen select "**emuMMC/EF00**"
1. Click "**OK**"
	* Now, when the STB starts up, it will automatically launch emuMMC.
	* To get into the official firmware, run **hekate -> Launch -> Stock**

{% endspoiler %}

{% spoiler Unstitched prefix with a chip from Team Xecuter (SX Core or SX Lite) %}

{% spoiler Preparatory work %}

Until we start the transition, we need to make sure that SysNAND and EmuNAND are running the latest version of the system software. Otherwise, when migrating EmuNAND to Atmosphere, you will not be able to run it.

#### Backing up saves

1. Back up the save files according to [this instruction](https://switch.customfw.xyz/backup-saves.html){: target = "_blank"}

#### Upgrading SysNAND to the latest system software

1. Turn on the console while holding the volume up button to access the SX OS bootloader menu
1. Go to "**Options**" -> "**SX Core**/**SX Lite**" -> "**Genuine boot**" -> "**Continue**" to run SysNAND
1. Wait for the download of the official firmware to finish
1. Go to "**System Preferences**" -> "**System**", click on "**System Update**"
* Wait for the firmware update, then turn off the console
* If your set-top box already has the latest version of system software, just turn off the console
* Yes, it is safe and will not result in a ban

#### Updating EmuNAND to the latest system software

1. Update EmuNAND to {% include /vars/update_version.txt %} by [this instruction](update-to-latest){: target = "_blank"}

{% endspoiler %}

{% spoiler Start firmware %}

1. Insert the memory card of the set-top box into the PC
1. Install {% include abbr/kefir_addr.txt %} by choosing "**Atmosphere for SX Core/Light**" as an option (`modcip.zip` for manual installation)
1. Wait for the installation to complete, then return the memory card to the console
1. Turn on the console
* SysNAND should load.
* If you encounter any errors, see the "[**Problems and Solutions**](migrate # problems-and-solutions)" section at the bottom of this page

{% endspoiler %}

{% spoiler Transferring EmuNAND from SX OS to Atmosphere %}

1. Turn off your console
1. Turn on the console while holding the volume up button to boot into hekate
1. Go to "**emuMMC**"
1. Click "**Migrate emuMMC**"
1. Select "**Emunand** -> "**Continue**"
1. After finishing the migration, click "**Change emuMMC**" and on the right side of the screen select "**emuMMC/EF00**"
1. Click "**OK**"
1. Go to "**Tools**" -> "**Backup eMMC**" -> "**eMMC BOOT0 & BOOT1**"
1. Press "**Close**", "**Close**", go to "**Home**" and press "**Power Off**", confirm shutdown
1. Insert the memory card of the set-top box into the PC
1. Go to the folder `sd: \ backup \% emmc_id%`, where**% emmc_id%**is a unique number for each separate STB.
1. Copy `BOOT0` and` BOO1` from this folder to the folder `emuMMC \ ED00 \ eMMC` with replacement
* Now, when the STB starts up, it will automatically launch emuMMC.
* To get into the official firmware, run**hekate** -> "**Launch**" -> "**Stock**"

{% endspoiler %}

{% spoiler Creation of EmuNAND via hekate %}

If you didn't have EmuNAND, it is highly recommended to create one. This is done primarily to avoid unpleasant consequences for SysNAND in case of any problems, so do EmuNAND even if you don't plan to use a license or online!
{: .notice - warning}

1. Turn off your console
1. Turn on the console while holding the volume up button to boot into hekate
1. Go to "**emuMMC**"
1. Click "**Create emuMMC**" -> "**SD File**"
* To create emuMMC you need to have at least 32GB of free space on the card! If you do not have that much, take another card, or temporarily transfer the Nintendo folder to your PC
1. After finishing emuMMC creation, click "**OK**"
* Now, when the STB starts up, it will automatically launch emuMMC.
* To get into the official firmware, run**hekate** -> "**Launch**" -> "**Stock**"

{% endspoiler %}

{% spoiler Backup firmware and keys %}

1. Turn off your console
1. Insert the memory card of the set-top box into the PC
1. Copy the `emuMMC` folder from the root of your memory card to your PC. This is your emunand. It is identical to the backup, so there is no point in creating a backup separately
1. Return the memory card to the console
1. Turn on the console while holding the volume up button to boot into hekate
1. Go to Payloads and select Lockpick_RCM.bin
1. Press the (Power) button, being on the first line in the program for dumping keys
1. Press the (Power) button again to go to the main menu of the program.
1. Use the volume buttons to move the cursor to the Power Off item and press the (Power) button to turn off the set-top box.
1. Insert the memory card of the set-top box into the PC
1. Go to the folder `sd:/switch` and copy the files` prod.keys` and `partialaes.keys` to the same folder where you copied your backup

Place the backup in a safe place, preferably several different ones. And into the cloud. And on a USB flash drive. Don't lose it!
{: .notice - danger}

{% endspoiler %}

{% endspoiler %}

## Problems and solutions

{% spoiler Black screen when starting SysNAND %}

1. Turn off the set-top box by holding the power button for 30 seconds
1. Insert the memory card of the set-top box into the PC
1. Download [SX_OS 3.1.0](https://t.me/SX_OS/178){: target = "_blank"}
1. Place `boot.dat` from the archive` SX_OS_v3.1.0_BETA_by_ [Team-Xecuter] .zip` into the root of the memory card with replacement
1. Turn on the console while holding the volume up button to access the SX OS bootloader menu
1. Go to "**Options**" -> "**SX Core**/**SX Lite**", then select**Cleanup** -> **Continue**
1. Press "**Power Off**" to turn off the console
1. Insert the memory card of the set-top box into the PC
1. Install {% include abbr/kefir_addr.txt %} by choosing "**Atmosphere for SX Core/Light**" as an option (`modcip.zip`)
1. Wait for the installation to complete, then return the memory card to the console
1. Turn on the console
* SysNAND should load.

{% endspoiler %}

{% spoiler Black screen when starting EmuNAND/Errors when starting EmuNAND related to boot %}

Try starting SysNAND first and only follow the instructions below if SysNAND starts! If not, fix this problem first and then go back to this tutorial!
{: .notice - warning}

1. Turn on the console
1. On the kefir screensaver**press the volume down button**to get into hekate
1. Go to "**Tools**" -> "**Backup eMMC**" -> "**eMMC BOOT0 & BOOT1**"
1. Press "**Close**", "**Close**", go to "**Home**" and press "**Power Off**", confirm shutdown
1. Insert the memory card of the set-top box into the PC
1. Go to the folder `sd: \ backup \% emmc_id%`, where **%emmc_id%** is a unique number for each separate STB.
1. Copy `BOOT0` and `BOO1` from this folder to the folder `emuMMC \ ED00 \ eMMC` with replacement
1. Try running emunand. If it doesn't work, you will have to create a new one.

{% endspoiler %}

{% spoiler Error "Pkg1 decryption failed! Is BEK Missing?" %}

Update {% include abbr/kefir_addr.txt %}!

{% endspoiler %}

{% spoiler I have another error %}

Tell us about it in the [group](http://vk.customfw.xyz).**Be sure to** attach a screenshot of the error, the version of your set-top box (if you don't know which - the serial), how the firmware starts (chip (if yes, which one), dongle (if yes, which one), somehow), version system software, the presence of EmuNAND, what exactly gives the error - EmuNAND or SysNAND, the version of kefir, after which an error occurs.
Missing **any** of these points will result in your post being deleted or ignored.

{% endspoiler %}