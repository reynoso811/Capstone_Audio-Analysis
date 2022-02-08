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

* Mel Frequency Cepstral Coefficients (mfccs) 

The MFCC feature extraction technique basically includes windowing the signal, applying the DFT, taking the log of the magnitude, and then warping the frequencies on a Mel scale, followed by applying the inverse DCT.

mffcs were extracted from each clip to train the models using 13 and 40 mffcs
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

* Baseline CNN
* Baseline RNN
* CNN and RNN with different mfcc's coefficients 
        

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

Please review my full technical analysis in [Notebook](https://github.com/reynoso811/Capstone_Audio-Analysis/blob/main/1)%20What%20is%20sound%20and%20EDA.ipynb) or my nontechnical analysis in [presentation](https://github.com/reynoso811/Capstone_Audio-Analysis/blob/main/Capstone%20-%20Audion%20Classification.pdf).

For any additional questions, please contact **Robert reynoso at robert@birdstop.io**

