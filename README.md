# DuckStation Patch

A patch for the [DuckStation](https://github.com/stenzek/duckstation) Android APK
that moves user data out of the restricted `Android/data` path and into
`/storage/emulated/0/DuckStation`, making it accessible to file managers
on Android 11 and later.

---

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
