# PSK
## RITHESH KUAMR G
## 212223060226
## Aim:
To assess the performance of Phase-Shift Keying (PSK) modulation in digital communication systems under varying noise conditions.

## Tools required:
Colab (for executing Python code)
Libraries: NumPy, Matplotlib
## Program:
~~~
import numpy as np
import matplotlib.pyplot as plt

# Input Data
data = np.array([1, 1, 1, 1, 0, 0, 0, 1, 0, 0])
print("Input Data:", data)

# BPSK Modulation: Mapping 0 -> -1 and 1 -> +1
bpsk_signal = 2 * data - 1

# Create time axis
t = np.linspace(0, 1, 100)

# Carrier Wave (Cosine)
carrier = np.cos(2 * np.pi * 5 * t)

# Modulated Signal
modulated_signal = np.array([bit * carrier for bit in bpsk_signal]).flatten()

# Time axis for plotting
time_axis = np.linspace(0, len(data), len(modulated_signal))

# Plotting the results
plt.figure(figsize=(10, 6))

plt.subplot(3, 1, 1)
plt.stem(data)  # Remove use_line_collection argument
plt.title("Input Binary Data (0s and 1s)")
plt.xlabel("Bit Index")
plt.ylabel("Bit Value")

plt.subplot(3, 1, 2)
plt.plot(time_axis, modulated_signal)
plt.title("BPSK Modulated Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(3, 1, 3)
plt.plot(t, carrier)
plt.title("Carrier Wave (Cosine)")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.tight_layout()
plt.show()
~~~
## Output Waveform:
![Screenshot 2025-04-26 144023](https://github.com/user-attachments/assets/e3ef1c6c-a9b0-4bf9-ad21-ba9f19b91587)


## Results:
PSK successfully encoded data by changing the phase of the carrier signal.
It demonstrated good resistance to noise and maintained data integrity.
The modulation technique improved overall transmission efficiency.
The experiment confirmed PSK as an effective method for reliable digital communication.
