# Acoustic classification of Rotary-wing and Fixed-wing aircraft using Deep Learning

![xray](https://github.com/reynoso811/Capstone_Audio-Analysis/blob/main/heloVSfixed.png)

**Author**: Robert Reynoso


January 07, 2022

## Business Problem

In the field of aviation, can we use deep learning to classify a helicopter/ fixed wing aircraft and to what degree of accuracy?

## Data

![wavfile](https://github.com/reynoso811/Capstone_Audio-Analysis/blob/main/Helo_wave.png)

* Instead of manually recording aircraft a Python library was used to download and convert YouTube video from mp3 to wav files.
* Each audio clip was then sliced into 15 sec clips
* Stored into 2 classes (Helo/Fixed)


* mffcs were extracted from each clip to train the models using 13 and 40 mffcs
![mffcs](https://github.com/reynoso811/Capstone_Audio-Analysis/blob/main/mfcc_1.png)

![spec](https://github.com/reynoso811/Capstone_Audio-Analysis/blob/main/mfcc_1.png)


## EDA (Exploratory Data Analysis)

* Distribution of classes
    - Helicopter
        - 210 clips
    - Fixed wing
        - 208 clips


## Models
![Test](https://github.com/reynoso811/Capstone_Audio-Analysis/blob/main/Model%20Summary.png)

* Baseline MLP (Multi Layer Perceptron) Model:
    - The best accuracy the MLP model could achieve was about 75%.
    
        - The instability in the model can be seen in the loss and accuracy curves. We can see the instability in the variance 
          of the curves on both graphs ranging from 5.00 to 25.00 %, at certain points without subsiding. This can be seen 
          with the divergence of both curves beyond 20 Epochs. The training data almost reachs perfection, while the testing 
          data fails to improve.
          
        - The model is overfitting, quite a bit. We can see around Epoch 20 on the Binary Accuracy graph that the model 
          doesn't not improve.
          
        - This model could be improved/tuned by using differnet activation functions, trying different optimizers, 
          including early stopping and different degrees of dropouts.
        
        
* Baseline CNN Model Model:
    - The best accuracy the MLP model could achieve was about 74%

        - Simple sequential model was used, starting with 5 double convolutional networks of kernel size (3, 3) and max pooling with pool size (2, 2).            Additionally has batch normalization and dropout
        
           
* Pre-trained Model (VGG16):
    - The best accuracy from the Transfer Learning CNN Model was about 94%:

        - This model was saved and used to make predictions on our validation data
        - This was done due to the high accuracy of this model


* Talos Tuned CNN Model:
    - The model is still running....
        - I will update this part upon completion...
        

##  Conclusion and Recommendation

* Pre-trained Model was the best model
    - Transfer learning generally refers to a process where a model trained on one problem is used in some way on a second 
      related problem.
        - VGG-16 is a dataset of over 14 million images belonging to 1000 classes
    - One or more layers from the trained model are then used in a new model trained on the pneumonia images.
 


## Next Steps: 

* Try different activation functions 


* Re-run tuned CNN


* Try to use Grad-CAM class activation visualization



***

## For More Information

Please review my full technical analysis in [Notebook](https://github.com/reynoso811/Image-Classification-Pneumonia-X-rays-/blob/main/Phase_04_MLP_CNN_talos.ipynb) or my nontechnical analysis in [presentation](https://github.com/reynoso811/Image-Classification-Pneumonia-X-rays-/blob/main/Phase_04%20-%20Image%20Classification.pdf).

For any additional questions, please contact **Robert reynoso at robert@birdstop.io**

