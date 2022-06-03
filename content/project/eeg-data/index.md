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

Fast Fourier Transforms (FFT) are a computationally efficient and quick method to decompose sinusoidal signals into their component frequencies. We can show this using a series of signals at 1, 5, 10, 20 and 45 Hz shown below:

![Figure 1 Each of the 5 individual sinusoidal signals](sim_signal_indiv.jpg "Figure 1. Each of the 5 individual sinusoidal signals.")

These 5 signals can be combined into a signal signal, with a gaussian random sample added to simulate noise. This combined signal can then be put through a finite impulse response (FIR) band-pass (3-30 Hz) filter to further reduce noise and target specific frequencies for signal decomposition.

![Figure 2 Combined figures with noise and band-pass filter](sim_signal_combined.jpg "Figure 2. Combined figures, with noise and band-pass filter")

Using a multi-taper power spectral density method of estimation, we can show the original frequencies used to create the combined signal, both before and after a band-pass filter is applied.

