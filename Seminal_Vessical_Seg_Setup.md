# Seminal Vessical Segmentation Setup

This tutorial walks you through how to set up a custom segmentation environment for segmenting Seminal Vessels, Prostate Peripheral, Central Gland, and Urethra from Multi-Modal Images. We assume that you have [Python 3.10](https://www.python.org/downloads/release/python-3100/) installed for this tutorial.

## Create new Python 3.10 Virtual Environment

In this example setup, I will be creating all necessary files in one directory arbitrarily called "SV_Segmentation". You will likely need to change your commands to match your naming convention.

1. Create a new directory:


## Create new Python3.10 Virtual Enviornment
In this example set up I will be creating all neccicary files in one directory which is arbitrarly called "SV_Segmentation". You will likely need to change your commands to match your naming convention. 

1. Create New Directory

``` 
mkdir SV_Segmenation
``` 

2. Enter the newly created directory: 

``` 
cd SV_Segmenation 
```

3. Create an empty Virtual Enviornment

``` 
python3.10 -m venv .venv/sv_seg_venv 
```


4. Activate the virtual environment:
- Windows:
  ```
  .\.venv\sv_seg_venv\Scripts\activate
  ```
- Linux/Mac:
  ```
  source .venv/sv_seg_venv/bin/activate
  ```

## Download and setup Monai/MonaiLabel

1. Ensure that the virtual environment is active.
Terminal should show the name of your virual enornment

#TODO ADD IMAGE HERE
2. Install Monai using Pip

For other install options and a more detailed explination consult (Monai Documentation)[https://docs.monai.io/en/stable/installation.html]
``` pip3 install 'monai[all]' ```

2. Clone the forked version of MonaiLabel:
```
git clone https://github.com/Ivan-E-Johnson/MONAILabel.git
```
This will Create a new Directory called `MonaiLabel`
3. Install requirements from requirements Files

- Windows:
    ```
    cd .\MONAILabel\
    pip3 install -r .\requirements.txt
    ```
- Linux/Mac:
    ```
    cd MONAILabel
    pip3 install -r requirements.txt
    ```
4. Run Setup.py
```
python3 setup.py develop

```

5. Check to ensure that Installed correctly 
``` pip3 freeze ```
#TODO ADD IMAGE HERE 
``` pip3 freeze | grep monai ```
#TODO ADD IMAGE HERE 

## Slicer Setup 
1. Download Slicer
If you have Slicer Version 5.2 installed already you can skip this step. Otherwise you can download Slicer 5.2 [here](https://download.slicer.org/). Select a Stable download based on your Operating System and Click donwload. If using linux once downloaded open the compressed file and extract to desired install location, I will export it to our newly created directory but install location is unimportant. If using Windows open downloaded file and follow the Setup Wizard, this allows you to choose a location to save the application. Again it is not important where you save this app as long as you know where it is to open the program. 

2. Set up MonaiLabel as Slicer Extention

3. [Optional] Set MonaiLabel to automatically open 

4. Connect to MonaiLabel Server
#TODO ADD IMAGE HERE

5. Start Segmenting


