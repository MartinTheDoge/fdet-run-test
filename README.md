# fDet
Website application for fake-news detection using modified AlBERT AI

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
if you have AMD GPU then (linux needed
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
from wikipedia import Wikipedia
import requests
import json

wiki = Wikipedia() 
text = "Your sentence here"
titles = wiki.search(text)
sentences = wiki.extract_page(titles[0])
json_conv = {titles[0]:sentences}

with open("json_wiki.jsonl", 'a', encoding="utf-8") as json_outp:
    json.dump(json_conv, json_outp, indent=4, separators=", ", ensure_ascii=False)
    json_outp.write("\n")

req = requests.get("http://127.0.0.1:8002/backend/eval_debug", params={"text":text}).json()
```
To briefly explain what this code does, it searches for a similarty in given sentence to find a title from Wikipedia that refers to it, it then extracts the page and converts it to a json  
After the AI processes those given values, you should expect all of these values: <br>
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

