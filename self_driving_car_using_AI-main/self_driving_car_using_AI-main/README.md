# Self-Driving Car Controller
This project implements a server-side controller for a self-driving car simulator using a deep learning model. The controller receives images from the simulator, processes them, and returns steering and throttle commands.

## Features
- Processes real-time image data from a driving simulator.

- Uses a trained neural network to predict steering angles.

- Adjusts throttle based on speed to maintain a speed limit.

- Socket-based communication using Flask-SocketIO.
## Project Structure
- ```drive.py```: Main script that receives telemetry data and sends control commands.

- ```model.h5```: Pre-trained Keras model for steering angle prediction.

- ```requirements.txt```: Python dependencies required to run the project.

- ```issue.txt```: Notes on a socket connection issue and solution.

# Getting Started
## Prerequisites
Install the required packages:
``` bash
pip install -r requirements.txt 

```
**Note**: Ensure you install the exact versions for python-socketio and python-engineio to avoid connection issues:
``` bash
pip install python-engineio==3.13.2
pip install python-socketio==4.6.1
```
## Running the Controller
1.Place your ```model.h5``` file in the ```model/``` directory.

2.Start the server with:
``` bash
python drive.py
```
3.Connect it to a compatible driving simulator (e.g., Udacity Self-Driving Car Simulator) on port ```4567```.

## Image Preprocessing
The input image is:

- Cropped to remove irrelevant areas.

- Converted to YUV color space.

- Blurred and resized to (200x66).

- Normalized for model input.

## Troubleshooting
If you're having trouble connecting the simulator to the server, refer to ```issue.txt``` or try the following:
``` bash
pip install python-engineio==3.13.2
pip install python-socketio==4.6.1
```
This resolves compatibility issues reported [in this GitHub thread](https://github.com/udacity/self-driving-car-sim/issues/131).

## License
This project is for educational and non-commercial use. Attribution to Udacity for the simulator and original inspiration.






