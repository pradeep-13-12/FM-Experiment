# FM

EXP NO: 4	GENERATION AND DETECTION OF FM


AIM:
To write a program for Frequency Modulation and Demodulation using SCILAB and to observe and measure the frequency deviation and the modulation index of FM.


EQUIPMENTS REQUIRED

•	Computer with i3 Processor
•	SCI LAB

THEORY:

Frequency modulation is a type of modulation in which the frequency of the high frequency (carrier) is varied in accordance with the instantaneous value of the modulating signal.
FREQUENCY DEVIATION f and MODULATION INDEX m f :
The frequency deviation f represents the maximum shift between the  modulatedsignal
frequency, over and under the frequency of the carrier.

We define modulation index m f the ratio between f and the modulating frequency
m= f / fm


FREQUENCY MODULATION GENERATION:
The circuits used to generate a frequency modulation must vary the frequency of a high frequency signal (carrier) as function of the amplitude of a low frequency signal (modulating signal). In practice there are two main methods used to generate FM.
Algorithm
1.	Define Parameters:
•	Fs: Sampling frequency.
•	T: Duration of the signal.
•	Fc: Carrier frequency.
•	Fm: Frequency of the modulating signal.
•	Beta: Modulation index, which controls the extent of frequency deviation.
2.	Generate Signals:
•	Modulating signal: Sinusoidal signal used for modulation.
•	Carrier signal: The high-frequency carrier signal.
•	Modulated signal: FM modulated signal calculated by varying the carrier frequency according to the modulating signal.
3.	FM Modulation:
•	Modulated signal is obtained by modulating the carrier signal with the modulating signal.
 
4.	FM Demodulation:
•	Differentiation: Computes the derivative of the modulated signal to extract frequency variations.
•	Envelope Detection: Takes the absolute value to retrieve the envelope of the signal.
•	Low-pass Filtering: Applies a Butterworth low-pass filter to smooth the envelope and recover the original modulating signal.
5.	Visualization:
•	Plots the modulating signal, carrier signal, FM modulated signal, and demodulated signal for analysis.



PROCEDURE


•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
•	Execute the code
•	If any Error, correct it in code and execute again
Verify the generated waveform using Tabulation and Model Waveform

MODEL GRAPH:

<img width="512" height="365" alt="image" src="https://github.com/user-attachments/assets/acd787bd-5281-4f1b-802f-1aa39fac9189" />


Program
```
clc; clear; close;

// Given parameters
Am = 11.9;      // Message amplitude
Ac = 23.8;      // Carrier amplitude
Fm = 580;       // Message frequency (Hz)
Fc = 5800;      // Carrier frequency (Hz)
Fs = 55000;     // Sampling frequency (Hz)
kf = 75;        // Frequency sensitivity (Hz per volt)

// Time vector
t = 0:1/Fs:0.005;   // 5 ms duration

// Message signal
m = Am * sin(2 * %pi * Fm * t);

// Integrate message signal for frequency modulation
int_m = cumsum(m) / Fs;

// FM Modulated signal
s_fm = Ac * cos(2 * %pi * Fc * t + 2 * %pi * kf * int_m);

// Plotting signals
subplot(3,1,1)
plot(t, m)
title('Message Signal')
xlabel('Time (s)')
ylabel('Amplitude')
xgrid()

subplot(3,1,2)
plot(t, cos(2 * %pi * Fc * t))
title('Carrier Signal')
xlabel('Time (s)')
ylabel('Amplitude')
xgrid()

subplot(3,1,3)
plot(t, s_fm)
title('FM Modulated Signal')
xlabel('Time (s)')
ylabel('Amplitude')
xgrid()

// Display tabulation of sample values
disp("   Time(s)      Message(V)   FM Modulated(V)");
for i = 1:10:length(t)
    mprintf("%10.6f   %10.4f   %10.4f\n", t(i), m(i), s_fm(i));
end
```


Output Waveform

<img width="1202" height="1106" alt="image" src="https://github.com/user-attachments/assets/734b57f6-8810-45cb-bd73-73f9909bdc77" />


Tabulation
![WhatsApp Image 2025-11-06 at 18 14 37_b094da25](https://github.com/user-attachments/assets/28bd3f8b-d417-4ccf-aa22-5143ea68d7bb)



Calculation
![WhatsApp Image 2025-11-06 at 18 16 26_c423a406](https://github.com/user-attachments/assets/8b1f45b6-4876-4483-9b91-ee563db686e0)



Frequency Deviation Practical = 

Modulation Index Practical	= 

Modulation Index Theoretical	=



RESULT:

Thus, the frequency modulation and demodulation is successfully done and the output is experimentally verified.


