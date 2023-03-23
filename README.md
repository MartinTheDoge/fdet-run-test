# fDet
Website application for fake-news detection using modified AlBERT AI

## Requirements
- All libraries in "requirements.txt"
- Python version 3.9.2 (update this once new version installed)
- CUDA-enabled device (if you have AMD graphics card see https://github.com/RadeonOpenCompute/ROCm)

## Installing all packages manually
Input all of these commands into powershell and wait for them to install and download (done automatically)
```powershell
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install farm-haystack
pip install fastapi
pip install yake
```
if you have AMD GPU then
```
sample text
```

## First time use
Clone this repository to your local machine using 
```gitattributes
git clone https://github.com/fDet/fdet.git
```
**Make sure that all packages from "requirements.txt" are installed** <br>
open this cloned repository in your desired editor and call TextValidate() class in backend/main.py using 
```py
TextValidate().main("Your sentence here")
```

## Text Benchmark and its values
For testing out AIBertas functionality, we use 2 common knowledge Czech sentences
```
Miloš Zeman had been president for 10 years
Andrej babiš said he would not help the Baltics and Poland if they were invaded
```
changing the sentences just a bit to see how the AI reacts to those changes
```
Miloš Zeman had been president for 4 years
Miloš Zeman had been president for 8 years
Miloš Zeman had been president for 15 years
Andrej babiš said he would not help the Baltics and Poland
```
and its values respectively <br>
Support: 72.1%, 80.8%, 72.7% and 84.5%

## fDetAPI
sample text

