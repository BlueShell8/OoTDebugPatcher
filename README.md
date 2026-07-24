# OoTDebugPatcher

A lightweight command-line tool to patch a standard Zelda: Ocarina of Time US ROM into a Debug ROM (`ZELOOTD.z64`). 

The tool functions completely stand-alone. The BPS patch data is embedded directly into the executable as a Base64 string and decoded in RAM at runtime.

## How It Works

1. Run the `OoTDebugPatcher.exe` (or run the python script via terminal).
2. Enter the path to your original **Zelda: Ocarina of Time (US)** ROM when prompted.
3. The tool patches the ROM automatically. 

The generated Debug ROM will be saved instantly as **`ZELOOTD.z64`** in the same directory as the patcher.

## Features & Compatibility

*   **Tested OS:** Windows 11 (Other platforms may work but are unsupported).
*   **Auto-Format Conversion:** Automatically detects and converts `.z64` (Big Endian), `.v64` (Byte-swapped), and `.n64` (Little Endian) formats into the correct format before patching.
*   **Built-in Integrity Check:** Performs a CRC32 checksum validation. If you provide the wrong version of the Zelda ROM, the program will safely abort and warn you.

## Technical Details

*   **No File Trash:** No temporary `.bps` patch files are written to your storage disk. Everything is decoded directly in the system memory.
*   **Source Patch:** The embedded data originates from the official `ZELOOTMA` (Master Quest Debug) `.bps` patch file.
