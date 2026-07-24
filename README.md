# OoTDebugPatcher

A lightweight command-line tool to patch a standard Zelda: Ocarina of Time US ROM into a Debug ROM (`ZELOOTD.z64`). 

The tool functions completely stand-alone. The BPS patch data is embedded directly into the executable as a Base64 string and decoded in RAM at runtime.

## How It Works (For Users)

1. Run the `OoTDebugPatcher.exe`.
2. Enter or drag-and-drop the path to your original **Zelda: Ocarina of Time (US)** ROM when prompted.
3. Press **Enter**.

The tool patches the ROM automatically. The generated Debug ROM will be saved instantly as **`ZELOOTD.z64`** in the same directory as the patcher.

## Features & Compatibility

*   **Tested OS:** Windows 11 (Other platforms may work but are unsupported).
*   **Auto-Format Conversion:** Automatically detects and converts `.z64` (Big Endian), `.v64` (Byte-swapped), and `.n64` (Little Endian) formats into the correct format before patching.
*   **Built-in Integrity Check:** Performs a CRC32 checksum validation. If you provide the wrong version of the Zelda ROM, the program will safely abort and warn you.

## Technical Details

*   **No File Trash:** No temporary `.bps` patch files are written to your storage disk. Everything is decoded directly in the system memory.
*   **Source Patch:** The embedded data originates from the official `ZELOOTMA` (Master Quest Debug) `.bps` patch file.

---

## How to Build the .exe (For Developers)

If you want to compile the Python script into a standalone Windows executable yourself, you can use **PyInstaller**.

1. Install PyInstaller via command line:
   ```bash
   pip install pyinstaller
   ```
2. Navigate to your script folder and build the one-file executable:
   ```bash
   pyinstaller --onefile OoTDebugPatcher.py
   ```
3. You will find the finished `OoTDebugPatcher.exe` inside the newly created `dist/` folder.
