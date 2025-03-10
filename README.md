# Math M148 Final Project
by Aayushi Choudhary, Justin Gong, Belle Ho, Danelle Lizardo, Jared Patel, Ved Phadke, Jessie Zhou

## Overview
This repository contains a project that investigates aesthetic chills—intense physiological responses triggered by various stimuli. Our goal is to understand how textual, audio, and visual features of different media (e.g., songs, videos) correlate with the presence and intensity of chills.

Using the ChillsDB 2.0 dataset (and additional sources such as YouTube transcripts and Genius lyrics), we extract and engineer features in three modalities:

**Text**: sentiment analysis, word embeddings, linguistic complexity \
**Audio**: MFCCs, spectrograms, tempo, timbre, PCA-reduced components \
**Visual**: brightness, contrast, color distribution, frame differences \

We combine these features to explore relationships with chills through clustering, classification, and regression models.

## Repository Structure
```
.
├── .ipynb_checkpoints/               # Jupyter auto-generated checkpoint folder
├── CSV files/
│   ├── .DS_Store                     # Mac OS metadata file
│   ├── Audio_Features_EDA.ipynb      # Exploratory data analysis for audio features
│   ├── embeddings_final_model.ipynb  # Final modeling notebook using text/audio embeddings
│   ├── hierarchical clustering.ipynb # Hierarchical clustering approach for stimuli
│   ├── k-means clustering and audio visuals.ipynb
│   │                                  # K-means clustering & audio data visualization
│   ├── text_processing.ipynb         # Text cleaning, sentiment, and feature extraction
│   ├── transcript_dataset_construction.ipynb
│   │                                  # Gathering transcripts from YouTube/Genius
│   ├── visual_features.ipynb         # Visual feature extraction & EDA
│   └── README.md                     # (Optional) existing README in this folder
└── CSV files/                        # Subfolder or same folder containing CSV/Excel data
    ├── .DS_Store
    ├── final_df.xlsx
    ├── final_text_df.csv
    ├── pca_audio_features.csv
    ├── pca_video_audio_features.csv
    ├── stim_df.csv
    ├── stimuli_videos.csv
    ├── text_df.csv
    ├── transcripts.csv
    └── ~$final_df.xlsx               # Temporary Excel lock file
```
Below is a quick description of the notebooks and data files:

## Key Notebooks

- `transcript_dataset_construction.ipynb`: Retrieves transcripts/lyrics from YouTube and Genius, cleans them, and constructs the core dataset of textual data.
- `text_processing.ipynb`: Further cleans text (removes stopwords, punctuation), performs sentiment analysis (TextBlob, VADER), and extracts linguistic features (word count, POS tagging, TF-IDF, NMF Topic Modeling).
- `Audio_Features_EDA.ipynb`: Loads and explores raw audio data, extracting MFCCs, spectrograms, tempo, and applying PCA for dimensionality reduction.
- `visual_features.ipynb` : Extracts brightness, contrast, color histograms, and frame differences from videos.
- `k-means clustering and audio visuals.ipynb`: Applies K-means clustering to audio features, analyzing patterns in chill-inducing vs. non-chill stimuli.
- `hierarchical clustering.ipynb`: Explores hierarchical clustering methods on various feature sets.
- `embeddings_final_model.ipynb`: Uses advanced text/audio embeddings and conducts final modeling.
## Data Files
- `stim_df.csv`: Primary dataset linking each stimulus to its textual, audio, and visual identifiers.
- `transcripts.csv`: Raw transcripts or lyric data obtained from YouTube or Genius (before processing).
- `text_df.csv / final_text_df.csv`: Processed textual features (e.g., sentiment scores, TF-IDF vectors, word counts).
- `pca_audio_features.csv / pca_video_audio_features.csv`: Principal Component Analysis outputs for audio (and combined audio-video) features.
- `final_df.xlsx`: Merged dataset of all modalities (text, audio, visual) for final modeling.
- `stimuli_videos.csv`: Metadata about the videos used (e.g., YouTube links, file names).

## Project Workflow
1. Transcript Acquisition (`transcript_dataset_construction.ipynb`)
- Retrieves transcripts from YouTube videos or Genius for song lyrics.
- Cleans and formats them for subsequent text processing.
2. Text Processing & Feature Extraction (`text_processing.ipynb`)
- Removes stopwords, punctuation, and encodes text properly.
- Performs sentiment analysis and calculates linguistic features (e.g., word count, POS tagging).
- Generates TF-IDF or other vectorized representations.
3. Audio Feature Extraction (`Audio_Features_EDA.ipynb`)
- Loads audio files, extracts MFCCs, spectrograms, etc.
- Reduces dimensionality using PCA or other methods.
4. Visual Feature Extraction (`visual_features.ipynb`)
- Downloads video files (where permitted), extracts frames, calculates brightness, contrast, color distribution.
5. K-Means & Audio Visuals (`k-means clustering and audio visuals.ipynb`)
- Explores grouping stimuli into chill vs. non-chill clusters.
6. Hierarchical Clustering (`hierarchical clustering.ipynb`)
- Applies hierarchical methods to compare cluster structures.
7. Final Embeddings & Models (`embeddings_final_model.ipynb`)
- Combines text/audio/visual data and trains final predictive models.
