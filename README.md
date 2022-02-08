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

* Spectrograms

A Fourier Transform decomposes the signal into its constituent frequencies and displays the amplitude of each frequency present in the signal.

A Spectrogram chops up the duration of the sound signal into smaller time segments and then applies the Fourier Transform to each segment, to determine the frequencies contained in that segment. It then combines the Fourier Transforms for all those segments into a single plot.

It plots Frequency (y-axis) vs Time (x-axis) and uses different colors to indicate the Amplitude of each frequency. The **brighter the color the higher the energy** of the signal.

![spec](https://github.com/reynoso811/Capstone_Audio-Analysis/blob/main/melspec_1.png)


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


1. We learned that it is possible to classify a helicopter or a fixed-wing aircraft with a high degree of accuracy


2. A simple CNN model with more mfccs performed the best at 97.3 % accuracy


3. Confidence in applying in a real world situation



## Next Steps: 

* Data augmentation on audio


* Use spectrograms instead of mfccs


* Test in real world conditions






***

## For More Information

Please review my full technical analysis in [Notebook](https://github.com/reynoso811/Image-Classification-Pneumonia-X-rays-/blob/main/Phase_04_MLP_CNN_talos.ipynb) or my nontechnical analysis in [presentation](https://github.com/reynoso811/Image-Classification-Pneumonia-X-rays-/blob/main/Phase_04%20-%20Image%20Classification.pdf).

For any additional questions, please contact **Robert reynoso at robert@birdstop.io**

