# fDet by ByteSpirit
Website application for fake-news detection using modified Roberta AI <br> 
This app was published under an open-source MIT license <br> 
Below is the complete guide on how to use it

## About us
We are a group of 5 people that decided to battle the endless war against fake news. <br> 
This fact checking AI was created over the course of 4 months. Come and see for yourself. <br>
Website: www.fdet.eu

## Requirements
- All libraries in "requirements.txt"
- Python version 3.9.2 (update this once new version installed)
- CUDA-enabled device (if you have AMD graphics card see https://github.com/RadeonOpenCompute/ROCm)

## First time use
Run a file called "server_run.bat" in main. This script run django server, FAST API server and installs + builds npm. <br>
After both of the servers successfully loading, go into backend/example.py. You should see this code:
```py
import requests
import json

text = "Your sentence here"

req = requests.get("http://127.0.0.1:8002/backend/[version]/[evaluation systems]", params={"text":text}).json()

print(req)
Available evaluation systems: /backend/v1/eval /backend/v1/eval_fast /backend/rag/eval /backend/rag/eval_DPR /backend/rag/eval_Ada /backend/rag/eval_BM25
Output examples: /backend/v1/dummy /backend/rag/dummy
```
Variable "text" is for inputting your own sentences and 
## Text benchmark and its values

## Known issues

