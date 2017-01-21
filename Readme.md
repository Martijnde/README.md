#SDC-Project-3-Keras-CNN-Clone-Human-Driving

#Preparing for the project
Before starting this project I did research about the best aproach to take for this project, I used this resources to get a good feeling 
about the purpose of the project and best techniques to counter problems when facing them, see all resources used listed below this page.

#Files in this repository
model.py - The script used to create and train the model.
drive.py - The script to drive the car. resubmit the original drive.py or make modifications and submit your modified version.
model.json - The model architecture.
model.h5 - The model weights.
Readme.md - This file explaining the structure of the used network and training approach for the project.


#Model structure:

I decide to use the Keras Sequential model with ... layers and ...., 


#Strategy:
I decided to follow the advise of my mentor and other classmates to use the great data Udacity provided, this to get the best model possible to perform well on the track 1 in the simulator after opimizing the model to run the training data. 


#First run of the model
The first run of the model performed great using 10 EPOCH's and batch size 64, this resulted in: loss: 0.0128 - val_loss: 0.0111.
But I decided to tweak the model even more, but I also kept in mind that I had to be carefull not to overfit the model, thus this
would mean no good for driving the track.

#Tweaking the model:
The parameters I tweaked were: Number of EPOCH's and the Batch sizes. 
This overview below shows the gains and losses the model suffered during tweaking it's parameters and the resulting loss & val_loss values, followed by the adjustments I made to optimize the the parameters of the model using the training datat to enable the car to perform best possible when running the drive.py file in the simulator.

Using 10 EPOCH's with batch size 64 resulted in this results at Epoch 10/10:
8064/8036 [==============================] - 44s - loss: 0.0128 - val_loss: 0.0111


Using 25 EPOCH's with batch size 64 resulted in even better results, both loss and val_loss were lower using 10 EPOCH's:
8064/8036 [==============================] - 48s - loss: 0.0112 - val_loss: 0.0101


Using 75 EPOCH's with batch size 64  resulted in a lower loss, but higher val_loss:
8064/8036 [==============================] - 42s - loss: 0.0103 - val_loss: 0.0111


Using 25 EPOCH's with batch size 128 resulted in....:











#List of used resources:
The Sequential model API:
https://keras.io/models/sequential/

Getting started with the Keras Sequential model:
https://keras.io/getting-started/sequential-model-guide/

Medium post about his P3 submission insights and used techniques by SDC student Vivek Yadav:
https://chatbotslife.com/using-augmentation-to-mimic-human-driving-496b569760a9#.4gg5ak9im

Medium post by SDC student Mohan Karthik, about the way he used some of the techniques of Vivek Yadav listed above:
https://medium.com/@mohankarthik/cloning-a-car-to-mimic-human-driving-5c2f7e8d8aff#.kd0sa7c2p

Medium post by Vivek Yadav in response to the Medium post of Mohan Karthik about using his earlier stated techniques:
https://medium.com/@vivek.yadav/cloning-a-car-to-mimic-human-driving-using-pretrained-vgg-networks-ac5c1f0e5076#.sb9f2warq

Medium post by Vivek Yadav about Driving performance of augmentation based deep learning technique using Udacity data:
https://medium.com/@vivek.yadav/driving-performance-of-augmentation-based-deep-learning-model-on-udacity-data-247d2234fc49#.iw0vyq7oo

Chatbotslife post by Vivek Yadav aboutLearning human driving behavior using NVIDIA’s neural network model and image augmentation  
https://chatbotslife.com/learning-human-driving-behavior-using-nvidias-neural-network-model-and-image-augmentation-80399360efee#.loapoqmru

End to End Learning for Self-Driving Cars from NVIDIA:
http://images.nvidia.com/content/tegra/automotive/images/2016/solutions/pdf/end-to-end-dl-using-px.pdf

Helpful guide for those of you looking for some hints and advice by Paul Heraty:
https://carnd-forums.udacity.com/questions/26214464/behavioral-cloning-cheatsheet
