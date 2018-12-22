# Autonomous-Car-
Machine learning using convolution neural network

Required:

raspberry pi
pi cam
compatibile rc car
motor driver l293d

Please create the respective files:

forward
idle
left
right
reverse
optimized_thetas

This project aims to build an autonomous rc car using supervised learning of a neural network with a single hidden layer. We have not used any Machine Learning libraries since we wanted to implement the neural network from scratch to understand the concepts better.

We will be referring the DC motor controlling the left/right direction as the front motor and the motor controlling the forward/reverse direction as the back motor. Connect the ```BACK_MOTOR_DATA_ONE``` and ```BACK_MOTOR_DATA_TWO``` GPIO pins(`GPIO17` and `GPIO27`) of the Raspberry Pi to the Input pins for Motor 1(`Input 1`, `Input 2`) and the ```BACK_MOTOR_ENABLE_PIN``` GPIO pin(`GPIO22`) to the Enable pin for Motor 1(`Enable 1,2`) in the L293D Motor Driver IC. Connect the Output pins for Motor 1(`Output 1`, `Output 2`) of the IC to the back motor.

Connect the ```FRONT_MOTOR_DATA_ONE``` and ```FRONT_MOTOR_DATA_TWO``` GPIO pins(`GPIO19` and `GPIO26`) of the Raspberry Pi to the Input pins for Motor 2(`Input 3`, `Input 4`) in the IC. Connect the Output pins for Motor 2(`Output 3`, `Output 4`) of the IC to the front motor.

The ```PWM_FREQUENCY``` and ```INITIAL_PWM_DUTY_CYCLE``` represent the initial frequency and duty cycle of the PWM output.

We have created five class labels namely ```forward```, ```reverse```, ```left```, ```right``` and ```idle``` and assigned their expected values. All class labels would require a folder of the same name to be present in the current directory.

The input images resize to the dimension of the ```IMAGE_DIMENSION``` tuple value during training. The ```LAMBDA``` and ```HIDDEN_LAYER_SIZE``` values represent the default lambda value and the number of nodes in the hidden layer while training the neural network.

All these values are configurable in ```configuration.py```.

The images for training are captured using ```interactive_control_train.py```, the car is controlled using the direction arrows and all the images are recorded in the same folder along with the corresponding key press.

After segregating the images into their corresponding class folders, the neural network is trained using ```train.py``` which takes two optional arguments - ```lambda``` and ```hidden layer size```;  default values would be those specified in the configuration file. At the command prompt, run the following command

Once we have the trained model, the RC car is run autonomously using ```autonomous.py``` which takes an optional argument for the trained model; default will use the latest model in the ```optimized_thetas``` folder. 

Please feel free to post your doubts on code through my linkedin link https://www.linkedin.com/in/uvais-karni-531a06147/
