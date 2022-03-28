# Bird Song Classifier

### Introduction

Scripts to train and test a machine learning model on bird song audio files

### Workflow

1. Audio files are converted to standard sample-rate of 44.1 kHz
2. Mel spectrograms are calculated for each file with a frame size of 1024 frames with Hamming windowing and no overlap
3. Spectral energy below 500 Hz is filtered out to reduce background
4. The root-mean-square energy in each spectrogram is then used to normalize
5. Mel spectrograms can now be used directly as features
6. Feature representations derived are all time series, so summarize each feature dimension independently by its mean and standard deviation
7. Classification is then performed using a random forest classifier (scikit-learn v0.15)