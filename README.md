# fDet by ByteSpirit
Website application for fake-news detection using modified AlBERT AI. <br> 
This is an open-source repository and can be used by anyone and here's is a complete guide on how to do it

## About us
We are a group of 5 people that decided to battle the endless war against fake news. <br> 
This fact checking AI was created over the course of 4 months. Come and see for yourself. <br>
Website: www.fdet.eu

## Requirements
- All libraries in "requirements.txt"
- Python version 3.9.2 (update this once new version installed)
- CUDA-enabled device (if you have AMD graphics card see https://github.com/RadeonOpenCompute/ROCm)

## Installing all packages manually
Input all of these commands into powershell and wait for them to install and download (done automatically)
```powershell
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install -r requirements.txt
```
if you have AMD GPU then (linux needed)
```
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/rocm5.4.2
```

## First time use
Clone this repository to your local machine using 
```gitattributes
git clone https://github.com/fDet/fdet.git
```
**Make sure that all packages from "requirements.txt" are installed** <br>
open this cloned repository in your desired editor an go to backend/example.py. <br>
You should see this code
```py
import requests

text = "Your sentence here"

req = requests.get("http://127.0.0.1:8002/backend/[evaluation system]", params={"text":text}).json()

Available evaluation systems: /backend/v1/eval_DPR, /backend/v1/eval_fast, /backend/rag/eval_DPR, /backend/rag/eval_ada /backend/rag/eval_bm25
Output examples: /backend/v1/dummy, /backend/rag/dummy
```
First, you need to start FAST API local server, you can do this by entering ```py api.py``` or ```uvicorn api:app --reload``` into python terminal <br>
After waiting a couple of seconds, you should see this output
```py
INFO:     Started server process [ProcessID]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Uvicorn running on http://127.0.0.1:8002/ (Press CTRL+C to quit)
```

After the AI processes the given text, you should expect these values: <br>
<br>
Claim <br>
Supports <br>
Refutes <br>
Evidence <br>
<br>
test
## Text Benchmark and its values
For testing out our modified AIBertas functionality, we use 2 common knowledge Czech sentences
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
```
1stAI: Percentage
2ndAI: Percentage
3rdAI: Percentage
```

## fDetAPI
sample text

