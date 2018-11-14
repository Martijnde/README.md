#SDC-Project-3-Keras-CNN-Clone-Human-Driving

#Files in this repository
model.py - The script used to create and train the model.
drive.py - The script to drive the car. (with modifications, the modified version will be explained below.
model.json - The model architecture.
model.h5 - The model weights.
Readme.md - Explaining the network structure, the model, training approach and used recources for the project.


#Preparing before starting the project
Before starting this project I did research about the aim of and the best aproach to take for a succesful submission for this very challenging project, so I used the resources to get a good feeling about the purpose of the project and best techniques to use, all resources that were viewed and used by me are listed below this page.


#Preprocessing the data
The data was resized to 64x64 format to make them smaller so the model could run faster, I also edited the format of the images to 64x64 in the drive.py file, to use the same format of the images when running. Next to this I splitted the data into train and validation sets and the images in both the train and validation datasets were normalized and shuffled. 


#Model structure
I decided to use the Keras Sequential model based on the NVIDIA model with 5 conventional layers and flatten, dropout and dense, this to optimize  

![alt tag](https://github.com/Martijnde/SDC-Project-3-Keras-CNN-Clone-Human-Driving/blob/master/CNN%20Model%20Project%203.JPG?raw=true)

#Strategy
I decided to follow the advise of my mentor and other classmates to use the great dataset Udacity provided, the first runs oon my own generated data were not good at all. The Udacity dataset enabled me to build and tweak the best model possible to perform well on in the simulator, before using the Udacity dataset I took a look and noticed that some of the pictures looked somewhat nooisy and bumpy, this are some examples of pictures we had to keep in mind when pre prosessing the data before training our model:

![alt tag](https://github.com/Martijnde/SDC-Project-3-Keras-CNN-Clone-Human-Driving/blob/a83f918811b98649755b1e8bf8da6b04bcfdfa68/Noisy%20Image%20Example%201.jpg?raw=true)

![alt tag](https://github.com/Martijnde/SDC-Project-3-Keras-CNN-Clone-Human-Driving/blob/a83f918811b98649755b1e8bf8da6b04bcfdfa68/Noisy%20Image%20Example%202.jpg?raw=true)

![alt tag](https://github.com/Martijnde/SDC-Project-3-Keras-CNN-Clone-Human-Driving/blob/a83f918811b98649755b1e8bf8da6b04bcfdfa68/Noisy%20Image%20Example%203.jpg?raw=true)


#First run of the model
The first run of the model performed great using 10 EPOCH's and batch size 64, this resulted in: loss: 0.0128 - val_loss: 0.0111.
But I decided to tweak the model even more, but I also kept in mind that I had to be carefull not to overfit the model, thus this
would mean no good for driving the track. Also the Adam optimizer was used by me for Stochastic Optimization, to help the model perform well doing pattern recognition on the noisy dataset (The images) to get the lowest error possible.

#Tweaking the model
The parameters I tweaked a lot to get the best model with the lowest error score were: Number of EPOCH's and the Batch size of the train and validation data runs. The overview below shows the gains and losses the model suffered during tweaking it's parameters and the resulting loss & val_loss score, followed by the adjustments I made to optimize the the parameters of the model using the training datat to enable the car to perform best possible when using the output files to get the car running wel on the autonomus mode on the tracks in the simulator. When finished optimizing the model used 25 EPOCH's and a Batch size of 64, 

Using 10 EPOCH's with batch size 64 resulted in this scores:

8064/8036 [==============================] - 44s - loss: 0.0128 - val_loss: 0.0111

Using 25 EPOCH's with batch size 64 resulted in even better results, both loss and val_loss were lower:

8064/8036 [==============================] - 48s - loss: 0.0112 - val_loss: 0.0101

Using 75 EPOCH's with batch size 64  resulted in a lower loss, but higher val_loss:

8064/8036 [==============================] - 42s - loss: 0.0103 - val_loss: 0.0111

Using 25 EPOCH's with batch size 128 resulted in the same loss as 25 EPOCH's with batch size 64, but a better vall_loss:

8064/8036 [==============================] - 42s - loss: 0.0114 - val_loss: 0.0094

Using 25 EPOCH's with batch size 256 resulted in this values:

8064/8036 [==============================] - 53s - loss: 0.0115 - val_loss: 0.0127

## Final model parameters, using 32 EPOCH's and with a batch size of 64:


![alt tag](https://github.com/Martijnde/SDC-Project-3-Keras-CNN-Clone-Human-Driving/blob/master/35%20Epochs.JPG?raw=true)

#Run the drive.py file on track one
I decided to try the trained model in the simulator track one after making changes to the model.py and drive.py file, the car performed good and this would mean the submission would pass on this rubrick I think.

First I tried the model using 10 epoch's, this resulted in a crash (car in water)
8064/8036 [==============================] - 38s - loss: 0.0116 - val_loss: 0.0109

Using 25 epoch's resulted in great results on track 1!!
8064/8036 [==============================] - 48s - loss: 0.0271 - val_loss: 0.0084


#Run the drive.py file on track two
I decided to try the trained model in the simulator whitout making changes to the drive.py file, the car performed not very good at track two, I have to proceed to p4 & p5 now to reach the deadlines, so I decided to not tweak the model again for training it to also perform well on track two because I have to focus on reaching the term one dealines on time. 


#List of used resources
Adam: A Method for Stochastic Optimization:
https://arxiv.org/abs/1412.6980v8

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
