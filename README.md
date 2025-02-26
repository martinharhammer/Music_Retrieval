# Music Retrieval (Shazam Implementation)

![](header.webp)


This repository contains an implementation of the audio identification algorithm described in the [Original Shazam Paper (Wang, 2003)](https://www.ee.columbia.edu/~dpwe/papers/Wang03-shazam.pdf). The algorithm utilizes audio fingerprint hashing for efficient and accurate audio retrieval.

## Features
- Extracts audio fingerprints from sound samples
- Matches audio queries against a database of known fingerprints
- Uses a robust hashing technique for fast retrieval
- Implements the core principles of the Shazam algorithm

## Installation
To run this notebook, you can install the required dependencies using Conda with the provided `environment.yml` file:

```bash
conda env create -f environment.yml
conda activate ir
```

## Usage
1. Load an audio file into the system.
2. The algorithm extracts unique fingerprints from the audio signal.
3. The fingerprints are then stored and used for matching against new queries.
4. The system identifies and returns the best-matching audio sample.

## How It Works
1. **Preprocessing**: The input audio is transformed into a spectrogram.
2. **Feature Extraction**: Key frequency peaks are detected and used to create unique fingerprints.
3. **Database Matching**: The fingerprints are compared against a stored database of known audio fingerprints.
4. **Result Output**: If a match is found, the corresponding audio file is identified and retrieved.

## Implementation Details
In this implementation, we focus on selecting anchor points and defining corresponding target zones from the peaks of the constellation map. We then compute the hashes and store them in a dictionary for efficient matching. To validate our approach, we experimented with four different configurations. We first conducted small-scale tests using the dataset from Milestone 2.1 and then extended our evaluation with an additional 60 tarballs (~34 thousand songs).

At the end of this notebook, you will find detailed visualizations, evaluations, and a comprehensive discussion of our thought process, results, and conclusions.

## Dataset
The data audio tracks used in this notebook can be found at [Freesound MTG-Jamendo](https://cdn.freesound.org/mtg-jamendo/raw_30s/audio-low/). We used Tarballs 00-60 for our database creation, which comprise approximately 34,000 tracks. Once downloaded, the tracks should be placed in the `tracks/` directory. The queries to test should be placed in the `queries/` directory.

## Query Generation

- **Original**: The unmodified 10-second segment.
- **Noise**: The segment with added Gaussian noise.
- **Coding**: A strongly compressed version of the segment.
- **Mobile**: A version recorded outdoors using a mobile phone.

## Data Organization
- **Full Tracks**: Stored in the `tracks/` folder.
- **Generated Queries**: Stored in the `queries/` folder.

**Note**: All audio files are saved in MP3 format.

## References
[Original Shazam Paper (Wang, 2003)](https://www.ee.columbia.edu/~dpwe/papers/Wang03-shazam.pdf)



