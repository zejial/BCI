# P300 Speller EEG Data Preprocessing

This README provides an overview of the preprocessing steps implemented in MATLAB for EEG data intended for use with a P300 speller application. The code focuses on selecting channels, filtering, baseline correction, and feature extraction.


## Dataset Overview

The final dataset is derived from EEG recordings of 55 participants engaged in a P300 speller task. Each participant was instructed to focus on specific characters within a speller matrix to spell out five-letter words. The dataset captures the brain's responses to these stimuli, with the data preprocessed for optimal feature extraction and subsequent analysis.

## Usage

After preprocessing, the data is organized into a `900 x 387` double matrix for each participant, with the rows representing trials and the columns encapsulating various data points:

- **Column 1**: Numerical representation of characters (A-Z, 1-9, and underscore '_'). Each number corresponds to the targeted character in the speller matrix during each trial.

- **Column 2**: Sequence Code - This indicates the sequence of the flashing groups (rows 1-6, columns 7-12) in the P300 speller task, which is used for decoding the EEG response to specific stimuli.

- **Column 3**: Labels - Binary indication of whether the trial was a target (1) or non-target (-1).

- **Columns 4-387**: Data Features - Comprising 384 features extracted through bandpass filtering, baseline correction, and decimation, these columns contain the reshaped EEG signals ready for machine learning applications.

### Experiment Design

The P300 speller experiment was designed to record EEG responses from participants as they focused on specific letters within a matrix to spell out five-letter words. Each letter within a word was the target of a series of flashing sequences, with the following information:

- **Participants**: 55 individuals participated in the study.

- **Word Length**: Each participant was tasked with spelling five-letter words, requiring focused attention on a series of selected characters over multiple trials.

- **Repetitions**: Each character within a word was subjected to 15 repetitions of the flashing sequence, enhancing the signal-to-noise ratio of the recorded EEG responses and improving the reliability of the data for feature extraction.





