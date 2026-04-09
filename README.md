# Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

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
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import hilbert

ac = 19.4
am = 9.7
fc = 3660
fm = 366
fs = 36600

t = np.arange(0, 2/fm, 1/fs)

e1 = ac * np.sin(2 * np.pi * fm * t)

plt.subplot(3,2,1)
plt.plot(t, e1)
plt.title("Message Signal")

e2 = ac * np.sin(2 * np.pi * fc * t)

plt.subplot(3,2,2)
plt.plot(t, e2)
plt.title("Carrier Signal")

e3 = (ac + (am * np.sin(2 * np.pi * fm * t))) * np.sin(2 * np.pi * fc * t)

plt.subplot(3,2,3)
plt.plot(t, e3)
plt.title("AM Modulated Signal")

demodulated_signal = np.abs(hilbert(e3)) - ac

plt.subplot(3,2,4)
plt.plot(t, demodulated_signal)
plt.title("Demodulated Signal")

plt.tight_layout()
plt.show()
```

 __Output__:
 
<img width="805" height="604" alt="AM  Modulation using python" src="https://github.com/user-attachments/assets/a9bc1205-7e9a-4b89-9ded-6fb7f9595dfc" />


 __Result__:
 Thus Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib is experimentally done and the output is verified


