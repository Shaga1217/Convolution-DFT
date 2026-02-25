# Digital Signal Processing Take-home Assignment

## Convolution and Discrete Fourier Transform (DFT)

### Overview

This assignment implements two fundamental operations in Digital Signal Processing (DSP):

1. **Convolution** using the Input-Side Algorithm
2. **Discrete Fourier Transform (DFT)** using the correlation method

All implementations are performed manually using Python without relying on high-level library shortcuts such as `numpy.convolve` or `numpy.fft`.

The work is provided as a Jupyter Notebook containing explanations, code implementations, and required plots.

---

## Environment Requirements

- Python 3.x  
- Jupyter Notebook  
- Required Python libraries:
  - `numpy`
  - `matplotlib`

Install dependencies (if needed):

```bash
pip install numpy matplotlib notebook
````

Run notebook:

```bash
jupyter notebook
```

---

## Part 1 — Convolution (Input Side Algorithm)

### Objective

To implement convolution manually and demonstrate noise reduction using a Moving Average Filter.

### Steps Performed

1. Generated a noisy sinusoidal signal:

   * Frequency: **50 Hz**
   * Sampling rate: **1000 Hz**
   * Duration: **1 second**
   * White Gaussian noise added

2. Defined impulse response:

   * **3-point Moving Average Filter**
   * ( h = [1/3, 1/3, 1/3] )

3. Implemented manual convolution:

   * Nested loop structure
   * Input-side accumulation method
   * Output length = ( N_x + N_h - 1 )

4. Visualization:

   * Time-domain plot of original noisy signal
   * Time-domain plot of filtered signal

### Observation

The moving average filter smooths the signal and reduces high-frequency noise components.

---

## Part 2 — Discrete Fourier Transform (DFT)

### Objective

To compute the frequency spectrum of a signal using the DFT correlation equations.

### Steps Performed

1. Generated composite signal:

   * **60 Hz sine wave**
   * **120 Hz sine wave**
   * Added white noise
   * Sampling rate: **1000 Hz**
   * Duration: **1 second**

2. Implemented manual DFT:

   * Computed Real component
     [
     ReX[k] = \sum_{i=0}^{N-1} x[i]\cos(2\pi ki/N)
     ]
   * Computed Imaginary component
     [
     ImX[k] = -\sum_{i=0}^{N-1} x[i]\sin(2\pi ki/N)
     ]

3. Calculated magnitude spectrum:
   [
   |X[k]| = \sqrt{ReX[k]^2 + ImX[k]^2}
   ]

4. Visualization:

   * Frequency axis computed as ( f[k] = kf_s/N )
   * Magnitude spectrum plotted from 0 to Nyquist frequency

### Observation

The magnitude spectrum shows prominent peaks near **60 Hz** and **120 Hz**, corresponding to the signal components.

---

## File Structure

```
DSP_Assignment.ipynb   # Main notebook (implementation + plots)
README.md              # Project description and instructions
```

---

## Notes

* All convolution and DFT computations were implemented manually.
* No built-in convolution or FFT functions were used.
* All plots include titles, axis labels, and gridlines as required.

---

## Conclusion

This assignment demonstrates practical understanding of:

* Time-domain signal filtering using convolution
* Frequency-domain analysis using manual DFT
* The relationship between time-domain signals and their spectral representation

These implementations reinforce foundational DSP concepts beyond optimized library abstractions.

```
```
