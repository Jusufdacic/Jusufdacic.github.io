# Digitization of Speech Signals: A Practical Application of Spectrogram Analysis

**Course** — Digital Signal Processing, Faculty of Traffic and Communications, University of Sarajevo
**Date** — June 2025 · **Grade** — 10/10 · **Tools** — MATLAB

📄 **[Read the full paper](./digitalna-obrada-govora.pdf)**

---

## Overview

Speech is a continuous analog signal, but every system that processes it — a voice assistant, a telephone codec, a speaker authentication system — works with discrete samples. This project follows that conversion end to end on real recordings, and examines what the resulting digital representation reveals about how a sentence was spoken.

The same sentence was recorded in three vocal modalities — **normal speech, whispering, and raised pitch** — so that the analysis compares the effect of vocal effort and articulation while holding the linguistic content constant.

## Method

The work covers the full signal chain:

**Acquisition and digitization** — the analog voice signal is sampled and quantized, with the sampling rate chosen against the Nyquist criterion so the speech band is preserved without aliasing.

**Time-domain analysis** — each recording is examined as a waveform, showing amplitude envelope, pauses, and the relative energy of the three modalities.

**Frequency-domain analysis** — the short-time Fourier transform (STFT) is applied to produce spectrograms, giving a joint time-frequency view. This is what makes the comparison possible: a plain Fourier transform would show which frequencies are present but not *when*, which is exactly the information that distinguishes whispered speech from voiced speech.

**Filtering** — a low-pass Butterworth filter removes high-frequency noise. The Butterworth response was chosen for its flat passband, which avoids introducing ripple into the speech band it is meant to preserve.

**Reconstruction** — the filtered signal is reconstructed through interpolation, and compared against the original to assess what the filtering removed and what it retained.

## Analysis

Each modality is compared across its time-domain waveform and its spectrogram, before and after filtering. The comparison examines how vocal effort changes the acoustic signal:

- how the energy distribution shifts between voiced and whispered production
- how raised pitch affects the position and spacing of spectral components
- what the filtering removes from each modality, and whether that differs between them

## Tool Comparison

The paper includes a survey of tools commonly used for speech analysis — **Praat, MATLAB, CSL, TF32, and WaveSurfer** — comparing their intended use, capabilities, and the situations where each is the appropriate choice.

## Applications

The closing section connects the method to systems that depend on it in practice: voice assistants and speech recognition, telecommunication codecs and bandwidth reduction, and speaker authentication, where the same spectral features that distinguish vocal modalities are used to distinguish speakers.

## Author

**Jusuf Dacic**
Faculty of Traffic and Communications, University of Sarajevo
[github.com/Jusufdacic](https://github.com/Jusufdacic) · [jusufdacic.github.io](https://jusufdacic.github.io)
