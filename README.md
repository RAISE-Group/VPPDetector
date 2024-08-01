## What is VPPDetector?
VPPDetector is a tool designed to detect variadic parameter pitfalls (VPPs) in Python code, i.e., an API with variadic parameters internally passes these parameters to other APIs that do not support variadic parameters. VPPDetector helps developers identify and avoid potential compatibility issues arising from VPPs.

## Prerequisites
- Linux (tested on Ubuntu 18.04.1)
- Python 3.9.12
- [PCART](https://github.com/PCART-tools/PCART): Download PCART's source code and put ```vppdetector.py``` into the root directory of PCART

## Usage
### Step1: Download different versions of one Python third-party library to the local environment using the pip command, and add the path into the tool code. The directory structure is as follows:
```
/home/usr/Packages/
├── library/
│   ├── version1/
│       ├── file1.py
│       └── file2.py
|       ...
|	├── version1
|   ├── version2
|   ...
```

### Step2: Detection
**Run Command**
```shell
python vppdetector.py
```

## Output
The final detection results are saved into a JSON file, which records the file and line number where each API is located in detail.

```
{
    "/home/zhang/Packages/aiohttp/aiohttp0.18.0/client.py": [
        {
            "aiohttp.client.ClientSession.get": 322,
            "_request": [
                325,
                "[125]"
            ]
        },
    ...
}
```
