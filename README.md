# Voice Activated Audio Recorder

This is a voice-activated audio recorder designed for scanner radio use. The program detects audio activity from a sound card and automatically starts recording once voice is detected. After recording, it waits for the next audio event.

## Changes from the Original Code

This repository is a modified version of the original [voice activated audio recorder by Kari Karvonen](https://github.com/oh1kk/voxrecorder). Below are the main changes made:

1. **Device Selection**: In the modified version, the device index is dynamically fetched through the `get_input_device_index()` function.
2. **Status Display**: The `show_status()` function has been enhanced to display the current volume levels and status (Voice or Silence).
3. **Recording Logic**: The recording logic has been slightly adjusted for more consistent trimming and silence handling. The recorder now waits for activity before starting and stops recording after a brief silence is detected.
4. **File Saving**: The recorded audio files are saved with a timestamp and stored in a specified directory (`~/vox-records`).

## Features

- Automatically detects sound activity.
- Records audio when a voice is detected.
- Normalizes audio levels, trims silence, and adds silence padding to prevent clipping.
- Saves audio files in WAV format with timestamps in the file names.

## Installation

To use the program, ensure that you have Python 3 and the required dependencies installed:

```bash
pip install pyaudio
