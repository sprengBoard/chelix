## How to flash new QMK files (such as keymaps) to the Chelix:

The Chelix is configured to use QMK's bootmagic lite feature for easy flashing. Follow these steps after you've modified the QMK files and are ready to flash them to the Chelix. Note: if editing the keymap, I recommend editing the default keymap in the via keymap folder so you can still use VIA for simple keymap changes.

### Step 1
>Ensure QMK is installed and up to date on your computer (see the [QMK Getting Started documentation](https://github.com/qmk/qmk_firmware/blob/master/docs/newbs_getting_started.md)).
  
### Step 2
>With the Chelix unplugged from the computer press and hold the upper thumb key (the only thumb key if your Chelix has four rows) on one half, then plug a USB-C data cable connected to the host computer into the controller on that half of the Chelix.
  
### Step 3
>Continue to hold the bootmagic key down for 3-5 seconds after the controller is plugged in and the green LED on the controller illuminates. Release the key; the controller should now be in bootloader mode and should be visible as a drive in your file explorer (Finder on MacOS).
  
### Step 4
>Open the Command Line Interface (CLI) on your computer, navigate to the same directory where you've saved the Chelix QMK files, then run the following command:
>
>**For left half:**
```qmk flash -kb chelix -km via -bl uf2-split-left```
>
>**For right half:**
```qmk flash -kb chelix -km via -bl uf2-split-right```
>
>You'll see the QMK files being compiled and a bunch of green [OK]s. Once you see the line ```Wrote [#] bytes to /Volumes/RPI-RP2/NEW.UF2``` the flashing process for that half of the Chelix is complete.
>
>If you receive any [Error] messages, thoroughly examine the messages for clues on what went wrong. Chances are it's something simple in the Chelix's QMK files that needs to be fixed.

### Step 5
>Repeat steps 2-4 for the other half of the Chelix, then enjoy typing!

