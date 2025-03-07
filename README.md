## YIN algorithm

The ability to detect pitch in complex audio signals is a fundamental problem in signal processing, with applications ranging from music analysis to speech recognition. While human perception intuitively identifies pitch even in harmonically rich or noisy signals, translating this process into computational algorithms remains a challenge. This project explores the **YIN algorithm**, a widely cited pitch detection method, which combines autocorrelation with cumulative mean normalization to accurately extract periodicity from audio waveforms.

To test the algorithm's performance, a synthetic audio signal with realistic harmonic overtones was generated to closely mimic the complexity of musical instrument sounds. I extended the autocorrelation function to use FFT for faster computation. The implementation successfully estimated the fundamental frequency with high precision, producing a result of $440.06$ Hz for a signal with an expected pitch of $440$ Hz. This outcome demonstrates the effectiveness of the YIN algorithm in detecting pitch from non-trivial waveforms. 


### The audio signal (A4)
A slightly messy signal which mimics how octave multiples of the fundamental frequency are present in stringed music signals.

![image](https://github.com/user-attachments/assets/e014a7b3-4ada-479f-8135-2d5ae2b8436c)

### Autocorrelation
The bread and butter of the algorithm, comparing the signal to a shifted version of itself and returning the similarity between the shifted and original for some range of possible shifts.

![image](https://github.com/user-attachments/assets/324312fc-7a36-4919-926f-79892611c7dc)

### Difference function, CMNDF
Some modifications done onto the autocorrelation curve to prevent picking the zero-lag peak.

![image](https://github.com/user-attachments/assets/0a04355d-fb6f-4d9b-8d5c-1ff9f59f07e3)

The final pitch is chosen as the first trough (peak) below a certain threshold.
