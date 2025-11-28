# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

 __Program__:
 ```
import numpy as np
import matplotlib.pyplot as plt
import IPython.display as display
import io
import base64

# Parameters
Am = 9.2       # Message amplitude
Ac = 18.4       # Carrier amplitude
fm = 580        # Message frequency
fc = 5800        # Carrier frequency
fs = 58000     # Sampling frequency (must be high for smooth signal)

t = np.arange(0, 0.01, 1/fs)   # Time vector

# Message Signal
message = Am * np.cos(2 * np.pi * fm * t)

# Carrier Signal
carrier = Ac * np.cos(2 * np.pi * fc * t)

# Modulation Index
m = Am / Ac

# AM Modulated Signal
am_signal = Ac * (1 + m * np.cos(2 * np.pi * fm * t)) * np.cos(2 * np.pi * fc * t)

# Demodulation (Envelope Detector)
demodulated = np.abs(am_signal)

# Plotting
plt.figure(figsize=(12,10))

plt.subplot(4,1,1)
plt.plot(t, message)
plt.title("Message Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,2)
plt.plot(t, carrier)
plt.title("Carrier Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,3)
plt.plot(t, am_signal)
plt.title("AM Modulated Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,4)
plt.plot(t, demodulated)
plt.title("Demodulated Signal (Envelope)")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.tight_layout()
plt.show()
 ```

 __Output__:

<img width="1189" height="990" alt="image" src="https://github.com/user-attachments/assets/2d0f9a9c-ea1c-4e0d-a6c3-8e10ab9b1e4c" />

 __Tabulation__:


![WhatsApp Image 2025-11-28 at 20 23 54_e5732b8a](https://github.com/user-attachments/assets/cbb97607-ad2e-4ce1-ae1f-8ebaa8d06575)

![WhatsApp Image 2025-11-28 at 20 23 55_1fe004f2](https://github.com/user-attachments/assets/fca3c636-778d-47fa-945a-92ce3cc7d7c7)




 __Result__:

The message signal carrier signal and amplitude modulation (AM) signal will be displayed in separate plots Thus, AM is implimented using Numpu and matplotlib.
