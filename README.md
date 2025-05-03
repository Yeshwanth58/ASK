# ASK
# Aim:
Write a Python program for the modulation and demodulation of ASK.
# Tools required:
Python 3.x
# Program
```
import numpy as np
import matplotlib.pyplot as plt

# Parameters
fs = 1000  # Sampling frequency
fc = 100   # Carrier frequency
bit_rate = 10  # Bit rate
t = np.arange(0, 1, 1/fs)  # Time vector

# Generating Random Binary Data
data = np.random.randint(0, 2, bit_rate)
bit_duration = 1 / bit_rate
bit_t = np.linspace(0, bit_duration, int(fs / bit_rate), endpoint=False)
signal = np.concatenate([np.ones_like(bit_t) * bit for bit in data])

# Carrier Signal
carrier = np.sin(2 * np.pi * fc * np.linspace(0, 1, len(signal), endpoint=False))

# ASK Modulation
ask_signal = signal * carrier

# Plot Signals
plt.figure(figsize=(12, 6))

plt.subplot(3, 1, 1)
plt.step(np.linspace(0, 1, len(signal)), signal, where='mid', label="Binary Data")
plt.legend()
plt.grid(True)

plt.subplot(3, 1, 2)
plt.plot(np.linspace(0, 1, len(carrier)), carrier, label="Carrier Signal")
plt.legend()
plt.grid(True)

plt.subplot(3, 1, 3)
plt.plot(np.linspace(0, 1, len(ask_signal)), ask_signal, label="ASK Modulated Signal")
plt.legend()
plt.grid(True)

plt.show()
```
# Output Waveform

![image](https://github.com/user-attachments/assets/3bc92720-b6a2-4be0-9f9a-000ee1991396)

# Results
Thus the ASK (Amplitude Shift Keying) is performed using python.
# Hardware experiment output waveform:

![image](https://github.com/user-attachments/assets/8a3d62db-96ba-4f00-8b6f-77259a6b34bd)

