---
summary: Use a Fast Fourier Transform to decompose electrical signals to infer brain wave state.
authors:
  - admin
url_video: ""
date: 2019-11-01T00:00:00Z
categories: []
external_link: ""
url_slides: ""
title: Signal Decomposition of EEG Data
tags:
  - electroencephalogram
  - EEG
  - Fast Fourier Transform
  - signal decomposition
  - brain waves
links: null
image:
  caption: null
  filename: featured
  focal_point: Smart
  preview_only: false
url_code: "https://github.com/ianarriagamackenzie/sigdecom_eeg"
url_pdf: "/project/eeg-data/SignalDecomp_FFT.pdf"
---
Above is a 10 second measurement from an A1-A2 electroencephalogram (EEG) lead, taken from a sleeping patient. We examine this data with a motivating example and application, using a Fast Fourier Transform (FFT), which is a computationally efficient and quick method to decompose sinusoidal signals into their component frequencies. We can show this using a series of signals at 1, 5, 10, 20 and 45 Hz shown below:

![Figure 1 Each of the 5 individual sinusoidal signals](sim_signal_indiv.jpg "Figure 1. Each of the 5 individual sinusoidal signals.")

These 5 signals can be combined into a signal signal, with a gaussian random sample added to simulate noise. This combined signal can then be put through a finite impulse response (FIR) band-pass (3-30 Hz) filter to further reduce noise and target specific frequencies for signal decomposition.

![Figure 2 Combined figures with noise and band-pass filter](sim_signal_combined.jpg "Figure 2. Combined figures, with noise and band-pass filter.")

Using a multi-taper power spectral density method of estimation, we can show the original frequencies used to create the combined signal, both before and after a band-pass filter is applied.

![Figure 3 Frequency Estimation no FIR filter](sim_psd.jpg "Figure 3. Frequency Estimation, no FIR filter.")
![Figure 4 Frequency Estimation 3 to 30 Hz FIR filter](sim_psd_fir.jpg "Figure 4. Frequency Estimation, 3-30 Hz FIR filter.")

We also apply multitaper PSD estimation to our EEG sample. In particular (because the patient was asleep) we focus on the lower frequencies (0.5 Hz - 40 Hz) as we expect there to be a large concentration of lower frequency brain waves.

![Figure 5 PSD Estimation of EEG Lead](sim_psd_fir.jpg "Figure 5. PSD Estimation of EEG Lead.")

While this result may seem surprising at first, it does seem consistent with the data and highlights several features. Within EEG data, there are several defined frequency bandwidths which are associated with various states of consciousness. As this patient is asleep, we see high concentrations of Delta (0.5 - 4 Hz) and Theta (4 - 8 Hz) brain waves, with minimal higher brain waves. It also is visually consistent with the plotted EEG lead, as there are large sinusoidal waves in the reading.