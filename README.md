# The Long Dark - MelonLoader Setup Guide for Linux/Steam Deck

This guide will help you install MelonLoader and mods for The Long Dark on Linux or Steam Deck.

## Why Use Proton?

The Long Dark has a native Linux version, but MelonLoader currently has compatibility issues with native Linux builds. By forcing the game to run through Proton, you'll use the Windows version in a compatibility layer, which works much better with MelonLoader.

---

## Part 1: Force Proton Compatibility

1. Open Steam
2. Find The Long Dark in your library
3. Click the small **cogwheel icon** next to the Play button
4. Select **Properties**
5. Go to the **Compatibility** tab
6. Check the box for **"Force the use of a specific Steam Play compatibility tool"**
7. In the dropdown menu, select **Proton Experimental**
8. Launch the game at least once and let it update completely
9. Close the game

---

## Part 2: Download MelonLoader Installer

1. Switch to **Desktop Mode** (if on Steam Deck)
2. Open **Firefox**
3. Go to https://melonwiki.xyz/
4. Download the **Linux native installer**
5. Open the file manager (**Dolphin**)
6. Navigate to your **Downloads** folder
7. Find **MelonLoaderInstaller.linux**
8. **Right-click** on it → **Properties** → **Permissions** tab
9. Check **"Is executable"** or **"Allow executing file as program"**
10. Close the properties window

---

## Part 3: Install MelonLoader 0.7.1 (For .NET Setup)

1. **Launch the MelonLoader installer** (double-click the file)
2. When prompted to add a game, select **The Long Dark** from the list
   - The installer automatically detects installed Unity games
3. Make sure the version dropdown shows **0.7.1** (or latest version)
   - Don't worry about "Enable Nightly Builds" - it doesn't matter for this step
4. Click **Install**
5. Look for grey text that says **"How do I start MelonLoader?"** - click it
6. **Copy the launch argument** shown (should look like: `WINEDLLOVERRIDES="version=n,b" %command%`)

---

## Part 4: Set Steam Launch Options

1. Go back to **Steam**
2. Open your **Library**
3. Find **The Long Dark** and open **Properties** again
4. Look for the **Launch Options** field
5. **Paste** the text you copied: `WINEDLLOVERRIDES="version=n,b" %command%`
6. Close the properties window
7. **Launch the game once**
   - This installs .NET 6 in the game's Wine prefix for MelonLoader to use
   - The game should load normally
   - Close the game when you reach the main menu

> **Note:** If the game freezes when exiting, just restart your device - this is a known quirk but doesn't affect functionality.

---

## Part 5: Downgrade to MelonLoader 0.6.6

1. **Open the MelonLoader installer again**
2. Select **The Long Dark**
3. In the **version dropdown**, select **0.6.6**
4. Click **Downgrade** (or Install)
5. Wait for the installation to complete

**Why 0.6.6?** This version is currently the most stable for modded gameplay. Version 0.7.1 was only needed to set up .NET support.

---

## Part 6: Install Mods

1. Launch the game once with MelonLoader 0.6.6
   - **Note:** The first launch may take a while - be patient!
   - Let it sit and load completely
2. A **Mods** folder will be created in your game directory
3. To find your game directory:
   - Right-click The Long Dark in Steam → **Manage** → **Browse local files**

### Adding Mods:

1. Download mods from the mod list (usually as .zip files)
2. **Extract** the mod files
3. Place the extracted files into the **Mods** folder:
   - **.dll files** go in the Mods folder
   - **ModComponent** folders go in the Mods folder
   - If a mod has a **Plugins** folder, those files go in a separate **Plugins** folder
4. **Do not** place the .zip file itself in the Mods folder

> **Linux Note:** When extracting, Linux often creates an extra containing folder. Make sure you move the actual mod files (DLLs and ModComponent folders) into the Mods folder, not a folder containing them.

### Important Mod Notes:

- **ModSettings** is recommended - it adds an in-game menu to configure mods
- **Avoid "Auto Updating Plugin"** - it can cause crashes on Linux
- Many mods require **ModComponent** - download it if mods aren't working

---

## Part 7: Backup Your Saves (Recommended)

Before modding, back up your save files:

1. Navigate to: `~/.local/share/Hinterland/TheLongDark/`
2. Copy your save folders to a safe location
3. Alternatively, use backup tools available on the modlist

---

## Troubleshooting

### Game won't launch after downgrading to 0.6.6:
- Be patient - first launch can take several minutes
- If it still doesn't work, we'll need the log file:
  1. Navigate to your game folder
  2. Open the **MelonLoader** folder
  3. Find **latest.log**
  4. Share this file when asking for help

### Installer won't open or keeps crashing:
- Make sure there's no **version.dll** file in the same folder as the installer
- This file is MelonLoader's hook and will try to hook into the installer itself

### Mods aren't loading:
- Verify files are **extracted** from zip files
- Check that .dll files are directly in the Mods folder
- Make sure you're running MelonLoader 0.6.6, not 0.7.1

---

## Additional Resources

- **MelonLoader Wiki:** https://melonwiki.xyz/
- **The Long Dark Modlist:** [Community modlist link]
- **Discord:** For live help, join the TLD modding community Discord

---

## Why Not Use Protontricks?

Older guides mention Protontricks and terminal commands. These methods are **outdated**. The native Linux MelonLoader installer handles everything automatically and is actually more stable than the Windows installer.

You don't need to touch the terminal for this setup!

---

**Credits:** This guide is based on instructions from Kibbles, the community's Linux modding expert.
