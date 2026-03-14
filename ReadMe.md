                             ReadMe

YourOwnApp is a local AI assistant application built with Python, CustomTkinter, Whisper, Coqui TTS, and PyTorch.

=====
## Features:
Local LLM connection (LM Studio)
Voice recording and transcription (Whisper)
Text-to-Speech (Coqui TTS)
GPU acceleration (CUDA if available)

=====
## Requirements:
• OS: Linux x86_64 (Ubuntu/Debian recommended)
• LM Studio
• Python 3.10

=====
## LM Studio  -- Setup and install

Step 1 — Download

Go to:
https://lmstudio.ai

Click:
Download Desktop App → Linux
This will download a file like:
LM-Studio-0.x.x-x64.AppImage
It will probably land in your Downloads folder.


Step 2: —Check the file name
Check the exact filename in your Downloads folder:
ls ~/Downloads
You should see something similar to: (LM-Studio-0.x.x-x64.AppImage)

Step 3: —Create Applications folder
To move your LM Studio from the Downloads folder to your Applications folder in Linux Mint, follow these steps:

To create the ~/Applications folder:
mkdir -p ~/Applications


Step 4: —Move the AppImage to Applications
Run this command:
mv ~/Downloads/LM-Studio-0.x.x-x64.AppImage ~/Applications/
This will move the LM Studio .AppImage file to the ~/Applications folder.

Step 5: —Make it executable 
After that, make the file executable:
chmod +x ~/Applications/LM-Studio-0.x.x-x64.AppImage
Now you should be able to run LM Studio by double-clicking the .AppImage file from your ~/Applications folder.

You can also launch it from the terminal:
~/Applications/LM-Studio-0.x.x-x64.AppImage

Step 6: —Enable Developer Mode
After launching LM Studio:
Go to Settings
Turn ON Developer Mode
then exit settings

Step 7: —Download and Load a Model
Go to the Model Search tab
and download a model 
and load it

Step 8: —Start the Local Server
Now Go to the Local Server tab
Click Start Server
Make sure it says running is on:
The local server address
http://127.0.0.1:1234
YourOwnApp connects to this address automatically.

=====
## YourOwnApp -- Setup and install

Step 1: —Install python3.10

Use the official Ubuntu toolchain PPA:

sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.10 python3.10-venv python3.10-dev

Then check:
python3.10 --version

You should see something like:
Python 3.10.x (for example: Python 3.10.20)


Step 2: —Install System Dependencies
Note:
All system dependencies
must be installed outside the venv.
 
sudo apt update

sudo apt install \
python3.10 \
python3.10-venv \
python3.10-tk \
python3-pip \
ffmpeg \
espeak-ng \
libsndfile1 \
portaudio19-dev \
libespeak-ng-dev


Just in case, you can verify that the dependencies are installed
using the quick tests below.

If one of them is missing, you can install it using the standalone
install command provided.

                           Python3.10 install and test

This step was already completed above.

Test
python3.10 --version

You should see something similar to:
Python 3.10.x

                          Espeak install and test
Install:
sudo apt install espeak-ng
sudo apt install libespeak-ng-dev

espeak test:
espeak-ng "hello world"

You should hear:
 A robotic voice saying "hello world".

                       tkinter install and test
Install
sudo apt install python3.10-tk

check to see if tkinter installed:
Test
python3.10 -m tkinter

you should see: 
a small popup window
with the tkinter version

                     portaudio install and test
portaudio19-dev 
sudo apt install portaudio19-dev

Test
python3.10 - <<EOF
import pyaudio
print("PortAudio installed successfully")
EOF

You should see:
PortAudio installed successfully

                     libsndfile install and test
libsndfile1

Install
sudo apt install libsndfile1

Test
python3.10 - <<EOF
import soundfile
print("libsndfile installed successfully")
EOF

You should see:
libsndfile installed successfully

                    ffmpeg install and test
ffmpeg:
 
Install
sudo apt install ffmpeg

Test
ffmpeg -version

You should see version information similar to:
ffmpeg version x.x.x


Step 3: —Download and Extract the App

Go to the GitHub Releases page and download:

YourOwnApp-for-Linux.zip

The file will usually download to:
~/Downloads

Extract the zip file
You have two options.

Option (1) — Graphical (easiest)

Open your Downloads folder
Right-click YourOwnApp-for-Linux.zip
Click Extract Here
This will create the folder:
YourOwnApp-for-Linux/

Option (2) — Terminal

Run:
cd ~/Downloads
sudo apt install unzip
unzip YourOwnApp-for-Linux.zip

This will extract:
YourOwnApp-for-Linux/

This is how your folder should look:
📁 File Structure
YourOwnApp-for-Linux/
├── your_own_v1.py
├── install.sh
├── run.sh
├── requirements.txt
├── your_icon.png
├── README.md
├── .gitignore
└── models/
    ├── whisper_small/
    │   └── small.pt
    └── coqui_tts/
        ├── model_file.pth
        ├── config.json
        └── speaker_ids.json



Step 4: —Move YourOwnApp-for-Linux to Applications
mv ~/Downloads/YourOwnApp-for-Linux ~/Applications/


Step 5: —To install
cd ~/Applications/YourOwnApp-for-Linux
chmod +x install.sh         # only once for this file
./install.sh

GPU Support:
If you have an NVIDIA GPU with CUDA installed, the installer will automatically install the CUDA version of PyTorch.
If no GPU is detected, it installs the CPU version.

Notes:
First launch may take time while models download.
Whisper and TTS models are stored locally.


Step 6: —Run the App
cd ~/Applications/YourOwnApp-for-Linux
chmod +x run.sh       # only once
./run.sh

Step 7: —To start app every time 
cd ~/Applications/YourOwnApp-for-Linux
./run.sh
==========================================================================
