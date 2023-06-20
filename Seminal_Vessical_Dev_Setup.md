# Seminal Vessical Developer Environment Setup

This tutorial walks you through how to set up a custom segmentation environment for segmenting Seminal Vessels, Prostate Peripheral, Central Gland, and Urethra from Multi-Modal Images. We assume that you have [Python 3.10](https://www.python.org/downloads/release/python-3100/) installed for this tutorial.

## Create a new Python 3.10 Virtual Environment

In this example setup, I will be creating all necessary files in one directory arbitrarily called "SV_Segmentation". You will likely need to change your commands to match your naming convention.

1. Create a new directory:


## Create new Python3.10 Virtual Enviornment
In this example setup, I will be creating all necessary files in one directory which is arbitrarily called "SV_Segmentation". You will likely need to change your commands to match your naming convention. 

1. Create New Directory

``` 
mkdir SV_Segmenation
``` 

2. Enter the newly created directory: 

``` 
cd SV_Segmenation 
```

3. Create an empty Virtual environment

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
The terminal should show the name of your virtual environment


2. Install Monai using Pip

For other install options and a more detailed explanation consult (Monai Documentation)[https://docs.monai.io/en/stable/installation.html]
``` pip3 install 'monai[all]' ```

2. Clone the forked version of MonaiLabel:
```
git clone https://github.com/Ivan-E-Johnson/MONAILabel.git
```
This will create a new Directory called `MonaiLabel`
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
These commands are used to see what packages are installed in you current virtual enviornment.
Display all installed Packages
``` pip3 freeze ```

Display Installed Monai Packages 
``` pip3 freeze | grep monai ```

## Slicer Setup 
1. Download Slicer
If you have Slicer Version 5.2 installed already you can skip this step. Otherwise, you can download Slicer 5.2 [here](https://download.slicer.org/). 
Select a Stable download based on your Operating System and Click download. 

If using Linux once downloaded open the compressed file and extract it to desired install location, I will export it to our newly created directory but the install location is unimportant. 

If using Windows open the downloaded file and follow the Setup Wizard, this allows you to choose a location to save the application. Again it is not important where you save this app as long as you know where it is to open the program. 

2. Open Slicer
I will show how to open Slicer from the command line but you can also navigate and start the application by using your Operating Systems File Navigation GUI. 
![thumbnail_Navigate to Slicer](https://github.com/Ivan-E-Johnson/MONAILabel/assets/106177326/2e4faae4-8496-482e-a1d4-0bebe5a1ffe0)

It is also important to note that if you chose a different install location these shell commands may need to be updated with your paths.
Windows:
```
cd '.\Slicer 5.2.2\'
.\Slicer.exe
```
Linux/Mac:
```
cd Slicer-5.2.2
./Slicer
```
3. Open Settings

![Open Settings](https://github.com/Ivan-E-Johnson/MONAILabel/assets/106177326/f0cf5d0e-f4b6-4258-a5e4-45b665ee0d63)


4. Select Modules

![thumbnail_Select Modules](https://github.com/Ivan-E-Johnson/MONAILabel/assets/106177326/849739b5-22c0-4b7d-bb60-9b0f4d036926)

5. Expand "Additional Module Paths"

![thumbnail_Expand Module options](https://github.com/Ivan-E-Johnson/MONAILabel/assets/106177326/436a9fe3-664e-40cb-9f69-186a5af66407)

6. Click the "Add" button
  This should open a new window that will allow you to navigate around your files

![thumbnail_Add Modules](https://github.com/Ivan-E-Johnson/MONAILabel/assets/106177326/68624247-53de-4f5b-93ad-cb833feacde6)

7. Navigate to Custom MonaiLabel Plugin Path
   ### THIS IS VERY IMPORTANT TO GET CORRECT!
   You must navigate within the MonaiLabel to the Slicer sub-directory. The path should be 'path_to_MONAILabel/plugins/slicer' and select the MONAILabel folder contained within. 
![thumbnail_AddMonaiLabel Path](https://github.com/Ivan-E-Johnson/MONAILabel/assets/106177326/4646d38c-0209-4453-82bd-2c652cc3ecd3)

Once this folder is Selected click "Select Folder". This should close the navigation window and you should the original settings screen again but with your path to the plugin added to the list.
![thumbnail_Successfull added Module](https://github.com/Ivan-E-Johnson/MONAILabel/assets/106177326/51e9852c-510d-4e4d-91c2-9c5040c0863c)

8. Reset Slicer
   You have to reset Slicer after adding your custom module paths before you will be able to use it. If everything is working 
9. Open Custom Plugin
![thumbnail_Open SequenceMonailabel](https://github.com/Ivan-E-Johnson/MONAILabel/assets/106177326/3ee986ad-f35a-4692-a560-a9f4184cd073)
10. Add Server
    Select the text box that says "MONAI Label Server" and enter the address. For this Demonstration, we used "http://ExampleServer:Port". Next hit the Green Refresh button next to the text box. This should populate a lot of the empty fields 
     ![thumbnail_Add Server ](https://github.com/Ivan-E-Johnson/MONAILabel/assets/106177326/7ff061af-7fb8-431a-9686-4259271048b8)

11. Start Segmenting!
    Hit the Next Sample button and you should be good to start segmenting
    
12. [Optional] Set MonaiLabel to automatically open
  Navigate back to "Modules" in application settings and you should see near the bottom of the screen "Default startup module". Click the drop-down and select our custom module. Restart Slicer and you should see our custom module open automatically.


