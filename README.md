# [PR] Wallpaper Engine Workshop Downloader 

## WIP (Work In Progress)
I’ve looked into the code of the `select_save_location()` function and I have a suggestion to avoid stupid errors:

Currently, the script checks if the selected folder contains `\projects\myprojects`. If the user selects the final folder directly (by mistake... *cough* happened to me), the script fails. 

I'm refactoring the code to make it smarter and more robust.

### What I'm working on:

- **Smart Path Detection**: The script now detects if it is already in a sub-folder (like `myprojects`) and adapts itself automatically instead of just blocking with an error message.
- **Improved Write Access (Feature for Mojalu75)**: I've added a dedicated function to test write access. The script only warns you if it actually lacks permissions, instead of asking for Admin rights for no reason.
- **Typo Fixes**: 
    - `Invaild` -> `Invalid`
    - `is not exist` -> `does not exist` (in the `run_command` function)

### Next Steps:
- [ ] **Folder Renaming**: Implement a post-download logic that reads `project.json` to rename the numbered folders (e.g., `12345678`) into the actual Wallpaper title.
- [ ] **Filename Sanitization**: Add a function to clean illegal Windows characters from titles.

---

[中文](README_zh.md)

A workshop download tool for Wallpaper Engine.

## Functions  

* Automatically the workshop item for Wallpaper Engine without your own Steam account.

## Dependies  

* <https://github.com/oureveryday/DepotDownloaderMod>

## Usage  

 * Please install [.NET 8.0 Runtime](https://aka.ms/dotnet-core-applaunch?framework=Microsoft.NETCore.App&framework_version=8.0.0&arch=x64&rid=win10-x64) first.

 1. Browse the workshop item you like in <https://steamcommunity.com/app/431960/workshop/>

 2. Copy the URL of the workshop item you like. For example, `https://steamcommunity.com/sharedfiles/filedetails/?id=1234567890`

 3. Run `WallpaperDownloader_en.exe` (Enginsh) or `WallpaperDownloader_zh.exe` (Chiense) and paste the workshop item URL into item box.

 4. Select the wallpaper engine file path (with folder `\projects\myprojects` included) and click the `Download` button.

## Bugs  

* For bugs please report in issues.
