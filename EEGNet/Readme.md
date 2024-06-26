# EEGNet P300 Speller Data Processing

This project processes EEG data for a P300 speller task and classifies the data using the EEGNet deep learning model. 

## Prerequisites

This project is developed using Python 3.7.16. Below are the required packages and their versions as used in the development environment:

- `mat73==0.40`
- `numpy==1.21.5`
- `scipy==1.7.3`
- `tensorflow==2.0.0` 
- `absl-py==1.3.0`
- `fftw==3.3.9` 
- `h5py==3.7.0` 
  
```sh
pip install mat73 numpy scipy tensorflow==2.0.0 absl-py fftw h5py
``````

## Model Configuration with Undownsampled Data

In this project, undownsampled EEG data is utilized to take full advantage of the original information. This approach ensures that no potentially critical temporal features are lost due to downsampling.

### Data Dimensions

The undownsampled data comprises 9824 features spread across 32 EEG channels. This is reshaped into `(batch_size, channels, time points per channel, 1)` to fit the EEGNet model.

- **Training data**: 1800x9824
- **Testing data**: 5040x9824
  
### EEGNet Model Details

The EEGNet model used in this project is configured to handle the dimensions derived from undownsampled data effectively. The model parameters are specifically tailored to optimize the processing of EEG data:

- **Number of Channels**: 32
- **Samples**: `time_points_per_channel` = 307
- **Dropout Rate**: Set at 0.5
- **Kernel Length**: 64
- **Filter Parameters**: F1=8, D=2, F2=16. 
- **Normalization Rate**: 0.25

## Model Performance

The EEGNet model showed consistent performance across training, validation, and testing phases, achieving an avg accuracy of 83% across 55 participants. 

- **Training Accuracy**: 83%
- **Validation Accuracy**: 83%
- **Testing Accuracy**: 82%
- **Letter Detection Accuracy**: The accuracy of letter detection across individuals showed significant variability. While some subjects reached over 90% accuracy within 15 repetitions, others struggled with accuracies as low as 20% or even lower.

