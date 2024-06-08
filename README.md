# Scream Detection System using Neural Networks and MFCC's

MFCC's play an important role in the field of speech processing. The ability to distinguish a scream from another sound largely depends on the highest frequency component in the
frequecy spectrum of the sound signal. However, just converting time domain signal to frequency domain might not be very optimal. Human ear has a cochlea which has more filters at lower
frequency and lesser ones at higher frequency. This functionality can be replicated by using MFCC's. Computing MFCC's involves the following steps:

## 1) Pre-emphasis
   The speech signal is passed through a digital filter in order to increase amplitudes of higher frequencies present.
## 2) Frame Division
   The signal is then divided into frames where each and every frame overlaps with one another. The overlapping length of the frame is equal to half of the overall length of the frame.
## 3) Windowing
   Once the signal is divided into several components, its important to smoothen the ends of each frame. If this is not done, unusual frequencies might occur in the frequency spectrum. 
   Hamming window is usually preferred.
## 4) FFT Transform
   Now perform the Fast Fourier Transform of each and every frame to compute the speech signal spectrum. Length of FFT is greater than or equal to frame length for better frequency
   resolution.
## 5) Mel Frequency Filter Bank
   Each and every frame is passed through the Filter Bank which is nothing but series of triangular band pass filters. Output of each frame is obtained and power is computed in logarithmic
   scale.


Neural Networks have been used to build the model. MFCC's were extracted for each and every sound signal in the training data. Due to different lengths of each sound signal, MFCC's had
different lengths. In order to create uniform matrix size, zero padding has been done to the features computing the maximum matrix dimensions. Flattening of the features was done to
create a 1-D numpy array and this was given as an input to our neural network. The flattened 1-D array size is chosen as the number of inputs in the first layer and correspondingly 2
hidden layers with 30 neurons and 10 neurons respectively have been chosen. The output layer has 2 neurons to identify whether given sound is a scream or not.
