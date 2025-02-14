# Voice Activated Audio Recorder

This is a voice-activated audio recorder designed for scanner radio use. The program detects audio activity from a sound card and automatically starts recording once voice is detected. After recording, it waits for the next audio event.

## Changes from the Original Code

This repository is a modified version of the original voice-activated audio recorder by Kari Karvonen. Below are the main changes made:

- **Device Selection**: In the modified version, the device index is dynamically fetched through the `get_input_device_index()` function.
- **Status Display**: The `show_status()` function has been enhanced to display the current volume levels and status (Voice or Silence).
- **Recording Logic**: The recording logic has been slightly adjusted for more consistent trimming and silence handling. The recorder now waits for activity before starting and stops recording after a brief silence is detected.
- **File Saving**: The recorded audio files are saved with a timestamp and stored in a specified directory (`~/vox-records`).

## Features

- Automatically detects sound activity.
- Records audio when a voice is detected.
- Normalizes audio levels, trims silence, and adds silence padding to prevent clipping.
- Saves audio files in WAV format with timestamps in the file names.

---

## Installation

### **1. Update the System**

Before installing packages, update the system:

```bash
sudo apt update && sudo apt upgrade -y
```

### **2. Install PortAudio Dependencies**

Before installing the software libraries, install PortAudio, which includes `portaudio.h`, required for `pyaudio`:

```bash
sudo apt install -y portaudio19-dev python3-pyaudio
```

### **3. Install System Dependencies**

The program requires `pyaudio`, `ffmpeg`, and `pydub`. Install the necessary dependencies:

```bash
sudo apt install -y ffmpeg
```

### **4. Install Python Libraries**

To install the required Python libraries globally, run:

```bash
pip3 install --break-system-packages pyaudio numpy pydub
```

If you encounter issues with `pyaudio`, install additional dependencies:

```bash
sudo apt install -y libasound2-dev libjack-dev
```

Then retry installing `pyaudio`:

```bash
pip3 install --break-system-packages pyaudio
```

### **5. Verify the Installation**

Check that all required libraries are installed:

```bash
python3 -c "import pyaudio, numpy, pydub; print('All libraries installed successfully!')"
```

### **6. Run VOX Recorder**

To start the program, run:

```bash
python3 vox_recorder.py
```

---

## Additional Commands

### **Check Available Audio Devices**

```bash
arecord -l
```

### **Check ffmpeg Version**

```bash
ffmpeg -version
```

### **Exit Virtual Environment (if used)**

```bash
deactivate
```

Now your VOX Recorder is ready to use! 🚀

