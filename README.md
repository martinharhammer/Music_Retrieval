# Music Retrieval System (Shazam-Inspired Implementation)

## Introduction

As part of a group project I created with the help of my colleagues an implementation of an audio identification system inspired by the algorithm presented in the [Original Shazam Paper (Wang, 2003)](https://www.ee.columbia.edu/~dpwe/papers/Wang03-shazam.pdf). The system uses audio fingerprinting and hashing techniques to achieve fast and accurate music retrieval.

## Features

- Extracts unique audio fingerprints from sound files.
- Efficiently matches audio queries against a database of fingerprints.
- Utilizes robust hashing for quick and reliable identification.
- Implements core concepts of the Shazam audio recognition algorithm.

## Usage

1. **Upload an audio file** to the system.  
2. **The algorithm generates fingerprints** from the audio signal.  
3. **Fingerprints are stored** and used to compare against incoming audio queries.  
4. **The system returns the best match** from the database.  

## How It Works

### 1. Audio Preprocessing

The input audio is converted into a spectrogram, allowing frequency and time-based analysis.  
This step transforms raw audio into a visual representation of frequencies over time, which is essential for identifying key features.

### 2. Feature Extraction

Prominent frequency peaks are detected from the spectrogram to create a set of unique fingerprints.  
These peaks represent the most distinguishable points in the audio, ensuring that fingerprints are both compact and robust against noise or compression.

### 3. Fingerprint Matching

The generated fingerprints are compared with those stored in the database using a hash-based lookup.  
This approach ensures quick and efficient matching, even when dealing with large datasets.

### 4. Result Identification

When a match is found, the system identifies the corresponding audio track from the database and retrieves information about the best match.

---

## Implementation Details

This project focuses on selecting anchor points from the constellation map of frequency peaks and defining target zones for hashing.  
The fingerprints are stored in a dictionary structure, allowing rapid comparison between incoming queries and existing database entries.

---

## Testing & Evaluation

We experimented with various configurations and datasets:

- **Initial tests:** Conducted using a small dataset to verify the system's basic functionality.  
- **Large-scale tests:** Performed with approximately **34,000 audio tracks** from the **Freesound MTG-Jamendo** dataset.  

### The notebook includes:
- Detailed visualizations of the fingerprint extraction process.  
- Evaluation metrics and performance analysis.  
- A comprehensive discussion of methods, results, and potential improvements.  

---

## Dataset

The audio data used in this project comes from the [Freesound MTG-Jamendo dataset](https://cdn.freesound.org/mtg-jamendo/raw_30s/audio-low/).  
We utilized **Tarballs 00-60**, which include roughly **34,000 tracks**.


## Query Types

To test the system’s robustness, several variations of audio queries were generated:

- **Original:** An unaltered 10-second segment of the track.  
- **Noise:** A segment with added Gaussian noise to simulate real-world interference.  
- **Compressed:** A highly compressed version of the audio to test the system against lower-quality files.  
- **Mobile:** A recording made outdoors with a mobile phone to assess the impact of environmental noise and recording quality.  

These variations help evaluate how well the system can handle different distortions and real-world conditions.
