# Vots2023_TrackerPRO

Official Python Implementation (VOTS2023 Challenge)

## Environment

### 1. Anaconda 

```
conda create -n python38 python=3.8
conda activate python38
pip install opencv-python
pip install numpy
pip install matplotlib
```

### 2. Toolkit
More information: https://www.votchallenge.net/howto/overview.html

```
pip install vot-toolkit
pip install vot-trax
vot initialize vots2023 --workspace <workspace-path>
ex) <workspace-path>: /home/vots2023/
```

## Running the code
More information: https://www.votchallenge.net/howto/overview.html

Original integration code: https://github.com/votchallenge/integration/tree/master/python

### 1. Download and extract the code

TrackerPRO_code.zip file

copy the "integration folder" and paste it to your workspace-path

```
ex) Before: /Downloads/TrackerPRO_code/integration/... 
    After: /home/vots2023/integration/...
```

### 2. Update trackers.ini file
You should update the "trackers.ini" file (/home/vots2023/trackers.ini)

Don't care about the file (/home/vots2023/integration/trackers.ini)

Q. How to find your own env_PATH? 
1) Open terminal
2) Activate your environment (ex: conda activate python38)
3) Find the path using this command: which python
```
[TrackerPRO]  # <tracker-name>
label = TrakerPRO # <tracker description>
protocol = traxpython
command = ncc_multiobject_manager # <execution .py file>
paths = <path-to-tracker-source-directory> # <execution .py file path>
ex) paths = /home/vots2023/integration/python
env_PATH = <additional-env-paths>;${PATH} # <Python path>
ex) env_PATH = /...(which python path);${PATH}
```

### 3. Execute code 
Before executing, please read the "Readme.txt" file (/home/vots2023/integration/python/Readme.txt)

You need to change or remove the "cv2.imwrite" path.

```
vot evaluate --workspace <workspace-path> <tracker-name>
ex) vot evaluate --workspace /home/vots2023/ TrackerPRO
```

### 4. Check result 
After running evaluation of a tracker and obtaining the raw results in the results directory, tracking performance can be calculated using the following command:
```
vot analysis --workspace <workspace-path> <tracker-name>
```

If you want to submit results as a part of a challenge, package them using the following command that will produce a zip file, with all the required data.
```
vot pack --workspace <workspace-path> <tracker-name>
Sign in and submit the .zip file: https://eu.aihub.ml/competitions/201#learn_the_details
```

## Thank you for
* [deepgaze](https://github.com/mpatacchiola/deepgaze/tree/master/deepgaze)

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
