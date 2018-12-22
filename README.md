# Development-Of-Autonomous-Downscaled-Model-Car-Using-Neural-Networks-And-Machine-Learning-

Please feel free to contact me through linkedin if you have any doubts regarding the project: https://linkedin.com/in/shreyas-ramachandran-srinivasan-565638117/

To see photos and videos from presentation/demo, visit: https://ssr1996.wixsite.com/shreyas-ssr/projects-patents


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



CONTROLLING THE CAR

The controlling process consists of 4 parts: 
 The sensor interface layer includes various programming modules worried about getting and time stamping all sensor information. 
 The discernment layer maps sensor information into inward models. The essential module in this layer is the PI camera, which decides the vehicle's introduction and area. 

Two distinct modules enable auto to explore in view of ultrasonic sensor and the camera. A street discovering module utilizes the PI camera determined pictures to discover the limit of a street, so the vehicle can focus itself along the side. At last, a surface evaluation module separates parameters of the present street to determine safe vehicle speeds.  The control layer is in charge of managing the controlling, throttle, and brake reaction of the vehicle. A key module is the way organizer, which sets the direction of the vehicle in controlling and speed space.  The vehicle interface layer fills in as the interface to the robot's drive-by-wire framework. It contains all interfaces to the vehicle's brakes, throttle, and controlling wheel. It likewise includes the interface to the vehicle's server, a circuit that manages the physical capacity to a significant number of the framework segments.

In the proposed system, the raspberry Pi is used to control the L293D board, which allows motors to be controlled through the raspberry pi through the pulses provided by it. Based on the images obtained, raspberry pi provides PWM pulses tocontrol the L293D controller. L293D is a 16 Pin Motor Driver IC as shown in Figure 9. This is designed to provide bidirectional drive currents at voltages from 5 V to 36 V. Fig 9 L293D Breakout Board It also allows the speed of the motor to be controlled using PWM. It’s a series of high and low. The Duration of high and low determine the voltage supplied to the motor and hence the speed of the motor.

PWM Signals:

The DC motor speed all in all is specifically relative to the supply voltage, so if lessen the voltage from 9 volts to 4.5 volts, then our speed turn out to be half of what it initially had. Yet, for changing the speed of a dc motor we can't continue changing the supply voltage constantly. The speed controller PWM for a DC motor works by changing the normal voltage provided to the motor.The input signals we have given to PWM controller may be a simple or computerized motion as per the outline of the PWM controller. The PWM controller acknowledges the control flag and modifies the obligation cycle of the PWM motion as indicated by the prerequisites. In these waves frequency is same but the ON and OFF times are different. Recharge power bank of any capacity, here, 2800 mAH is used (operating voltage of 5V DC), can be used to provide supply to central microcontroller. The microcontroller used will separate and supply the required amount of power to each hardware component. This battery power pack is rechargeable and can get charged and used again and again.
