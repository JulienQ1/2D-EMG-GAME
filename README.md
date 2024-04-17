## Table of contents :
1) Introduction
2) Installation
3) How to use Opensignals
4) User Guide

## 1) Introduction

"2D-EMG-Game" is a Python script with a Tkinter-based GUI designed to recover EEG and EMG data from sensors available in our lab. The processed signals can be sent to other software, such as Unity, using the TCP communication protocol.

## 2) Installation

To use Thought in Motion, follow these steps to set up and run the project:

### Prerequisites

Ensure you have the following software and libraries installed on your system:

- [Python](https://www.python.org/downloads/) (version X.X.X recommended)
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) (optional but recommended for cloning the repository)

### Clone the Repository

Clone the Thought in Motion repository to your local machine. Open a terminal and run the following command:

```bash
git clone https://github.com/your-username/thought-in-motion.git
```

### Navigate to the project directory

Change into the project directory :

```bash
cd thought-in-motion
```

### Install the dependencies

Install the required Python libraries using the following command:

```bash
pip install -r requirements.txt
```

### Run the program

Run the main script to launch the GUI:

```bash
python main.py
```

## 3) How to use Opensignal

https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/7a230126-4476-4849-8e13-cfb74b47d23d



# Tutorial How to use Opensignals

![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/b8a98b20-a8ef-4f4c-b33a-356bb03b02cb)
![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/f0a7ef04-a7eb-4a81-8bbd-463712dd5d98)
![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/83e1a996-97d0-4042-a640-f85c4ab62091)
![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/07cc8092-41f1-409f-a40a-028f968b522a)
![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/b9e6d4b5-8c26-40a2-af35-db92ad90bf64)
![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/1ba4d883-8db8-44c2-bcbb-c6c4ada1f96c)
![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/6ad86e64-37a0-4065-bf4a-9c1e190720e7)
![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/f3d7cc0f-5ed6-40b6-a2d2-125711b59e9c)
![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/ef359856-07b8-4911-9e99-26ff529dc602)
![image](https://github.com/JulienQ1/EMG-Gamepad/assets/116632934/a15b4058-fbc8-4a73-861d-89d07092231d)


## 4) User Guide

### GUI Overview 

The GUI starts by showing a listbox with the two types of data supported for the moment. To continue, select the type of data, you want to use by clicking on it.

<img width="136" alt="GUI Accueil" src="https://github.com/HDevoille/Thoughts-In-Motion/assets/113013403/52797409-f012-47e1-b089-0743bf52124a">

After that, based on the type of data you selected a new menu will appear with several options.

#### EEG GUI Overview

<img width="761" alt="EEG GUI Overview" src="https://github.com/HDevoille/Thoughts-In-Motion/assets/113013403/79de2466-acea-4472-8e06-3bb3d179e662">

The EEG GUI contains a listbox with the name of the two EEG headset that we have in the lab. Selecting the headset will print the name of the EEG channels. 

To connect the EEG headset, you must first click the Resolve Stream button, once the stream is found, the inlet will be created and it will be printed in the console

The Preview Stream button will show one second of data. It is really useful to quickly inspect the data. 

Under these two buttons, you will find two checkboxes to activate both a Notch filter and a band pass frequency filter. When checked, an Entry will appear next to the checkbox for you to write the value for the filter. 

The path to model entry allow you to specify the filepath for your IA model and the load model will allow the script to load the model and use it to do predictions. Note : Your model must be saved using the joblib lib and must be .joblib file. 

The Epoch duration Entry allows you to choose the length of the epochs to use for the prediction. 

Finally, the Launch Server button will open a port on your computer and listen for new connexions. When a new connexion occurs, a message will be printed in the console and after that, the different output sent will also be printed in the console. 

#### EMG GUI Overview

<img width="896" alt="EMG GUI Overview" src="https://github.com/HDevoille/Thoughts-In-Motion/assets/113013403/88109aa5-8c45-4881-a978-e593c8af2ca7">

The EMG GUI has the same Resolve Stream and Preview Stream button that the EEG GUI. 

Under them, you will see a Calibration button. When clicked, this button will trigger the start of the calibration phase. During the calibration phase, the user should contract his muscle to obtain the maximal contraction value. The calibration phase lasts 5 seconds.

Once the calibration phase is over, the user can choose the Ratio to the max value by writting it in the Entry next to the calibration button. 

The Launch Server button works in the same way that the one from the EEG GUI. The output will be reduce to 0 when the value of the EMG is below the threshold which is determinded by the Ratio set by the user and the max value recorded during the calibration phase.






