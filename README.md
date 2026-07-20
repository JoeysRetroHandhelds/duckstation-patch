# DuckStation Patch

[![Join our Discord](https://img.shields.io/badge/Discord-Join%20our%20Community-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://joeysrh.link/discord)

A patch for the [DuckStation](https://github.com/stenzek/duckstation) Android APK
that moves user data out of the restricted `Android/data` path and into
`/storage/emulated/0/DuckStation`, making it accessible to file managers
on Android 11 and later.

## Important licensing and project notice

This is an unofficial, independently maintained patching project. It is not affiliated with, endorsed by, or supported by DuckStation or its developers.

DuckStation is copyright its respective authors, including Connor McLaughlin, and is distributed under the Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International licence:

https://github.com/stenzek/duckstation
https://creativecommons.org/licenses/by-nc-nd/4.0/

The supplied `duckstation-android.apk` is an unmodified DuckStation APK and remains subject exclusively to DuckStation’s licence and copyright terms.

The `duckstation-android-root-storage.xdelta` file was created by Joey’s Retro Handhelds. It contains binary differences intended to be applied to the specifically identified DuckStation APK. Applying the patch creates a modified DuckStation APK. The resulting APK is unofficial and is not provided or supported by the DuckStation project.

This repository does not grant permission to use, modify, or redistribute DuckStation beyond the permissions granted by DuckStation’s copyright holders.

This project is provided for noncommercial use only. No fee is charged for access to the APK, patch, instructions, or resulting software.

Do not contact the official DuckStation project for support with this patch or a patched installation.

## Required source APK

This patch applies only to the following unmodified DuckStation Android APK:

* Version: `0.1-8969-g611bb8fb4`
* SHA-256: `28F1528DFFB87A761AB1997A5D23BB62C5AA191B3A242A79A9BAEB3629B206F5`
* Original project: https://github.com/stenzek/duckstation

Do not apply this patch to another DuckStation release. Verify the APK’s SHA-256 checksum before applying the patch.

## What this patch does

- Adds the `MANAGE_EXTERNAL_STORAGE` permission
- Prompts for "All files access" on first launch
- Stores all user data in `/storage/emulated/0/DuckStation` once permission is granted
- Falls back to the default `Android/data` path if permission is denied

## Installation

1. Download `duckstation-android.apk` and `duckstation-android-root-storage.xdelta`
   from the [latest release](../../releases/latest)
2. Open [UniPatcher](https://github.com/btimofeev/UniPatcher), select `duckstation-android-root-storage.xdelta`
   as the Patch file and `duckstation-android.apk` as the ROM file, then select an Output file
   and tap Save — this creates `duckstation-android [patched].apk`
3. Uninstall the original DuckStation if installed
4. Install `duckstation-android [patched].apk`

## Migrating existing data

If you have saves, memory cards, BIOS files, or settings from a previous install:

1. **Before uninstalling**, open DuckStation → Settings → Transfer Data → Zip file → **Export**,
   give the ZIP a name and save it somewhere safe
2. Uninstall the original DuckStation
3. Install the patched version and grant "All files access" when prompted
4. Open DuckStation → Settings → Transfer Data → Zip file → **Import**,
   choose the ZIP from your export

Your data will be placed into `/storage/emulated/0/DuckStation` automatically.
