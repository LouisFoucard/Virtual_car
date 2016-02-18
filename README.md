# Virtual_car
This project proposes to use a convolutional Neural network to control a Self-driving car in virtual environment generated by the Blender Game Engine. 

The network is a classifier: given an input raw image, it classifies it into a turn left, go straight or turn right class. The resulting command is then sent to the Blender Game Engine, which updates the car position, renders a new image, and sends it back to the neural network to determine the next command.

First, the data used for training is generated by manually driving around the track. Each images is stored with the corresponding user command at the time when the image was taken (left/straigth/right). This is handled by the Get_training_data.ipynb python notebook (which takes care of receiving and storing images and commands) and the Get_training_data_Circ1.blend blender file.

The neural network is then trained using the Trainer.ipynb ipython notebook, with Theano/lasagne implementation. The loss  function used here is binary cross-entropy for the different command classes.

Once trained, the Driver.ipynb python file can be launched to directly and autonomously control the virtual car. 

Here is a screen shot of the simple model for a car and track in the blender game engine:

![alt tag](https://github.com/LouisFoucard/Virtual_car/blob/master/virtual_car.png)

Upcoming updates include: 
- use of batch normalization to accelerate the training of the neural network. 
- replace the ad hoc UDP communication with the Blender-python interface module (Blender Learning Environment) that I recently 
developed for machine learning purposes (https://github.com/LouisFoucard/BLE_python_interface)


