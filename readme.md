# Digit Recognition System

This project implements a digit recognition system from scratch that processes audio files to identify spoken digits from 0 to 9. Utilizing a custom Gated Recurrent Unit (GRU) architecture, the model leverages digital signal processing techniques to transform audio signals into features suitable for classification.

## Dataset Overview

The dataset consists of **120 audio files**, categorized into:

- **Training Dataset**: 96 audio files (80% of the total)
- **Testing Dataset**: 24 audio files (20% of the total)
- **Audio File Format**: WAV
- **Sampling Frequency**: 8 kHz
- **Length per File**: Approximately 1 second
- **Total Features**: 14 (13 Mel Frequency Cepstral Coefficients (MFCCs) + 1 Zero-Crossing Rate (ZCR))
- **Total Classes**: 10 (Digits 0 to 9)

### Digital Signal Processing Parameters

- **Frame Length**: 256 samples (32 ms)
- **Hop Length**: 128 samples (16 ms)
- **Total Frames per File**: 59

This structured approach to framing allows us to efficiently extract features from the audio signals, facilitating better model training and performance.

## Hyperparameters

To achieve optimal results, we fine-tuned the following hyperparameters:

- **GRU Layers**: 1
- **GRU Activation Function**: tanh
- **Output Activation Function**: Softmax
- **Loss Function**: Categorical Cross Entropy (CCE)
- **Number of Neurons**: 64
- **Sequence Length**: 59
- **Learning Rate**: 0.001
- **Optimizer**: Adam
- **Epochs**: 200

These parameters were chosen to balance model complexity and performance, ensuring that our system learns effectively without overfitting.

## Performance Results

![Model Architecture](https://firebasestorage.googleapis.com/v0/b/common-e8332.appspot.com/o/cce_gru.png?alt=media&token=6b4a516a-ec56-4bd6-aeba-257219883494)

![Model Architecture](https://firebasestorage.googleapis.com/v0/b/common-e8332.appspot.com/o/accuracy_train.png?alt=media&token=e52452d5-ba08-465b-8055-cb99bea8241c)

![Model Architecture](https://firebasestorage.googleapis.com/v0/b/common-e8332.appspot.com/o/accuracy_gru_test.png?alt=media&token=4ee36e59-7ff4-4ddb-b75f-6efeaf2dd656)

The model demonstrated impressive results, showcasing its effectiveness in recognizing digits:

- **Training Dataset Accuracy**: 100.00% 
- **Training Dataset Loss (CCE)**: 0.0148
- **Testing Dataset Accuracy**: 100%
- **Testing Dataset Loss (CCE)**: 0.0598

### Confusion Matrix 

![Model Architecture](https://firebasestorage.googleapis.com/v0/b/common-e8332.appspot.com/o/cm_gru.png?alt=media&token=2c57dd0d-e158-47cb-9034-498657e377eb)

### Classification Report

| Digit | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 1.00      | 1.00   | 1.00     | 2       |
| 1     | 1.00      | 1.00   | 1.00     | 3       |
| 2     | 1.00      | 1.00   | 1.00     | 3       |
| 3     | 1.00      | 1.00   | 1.00     | 2       |
| 4     | 1.00      | 1.00   | 1.00     | 3       |
| 5     | 1.00      | 1.00   | 1.00     | 2       |
| 6     | 1.00      | 1.00   | 1.00     | 2       |
| 7     | 1.00      | 1.00   | 1.00     | 2       |
| 8     | 1.00      | 1.00   | 1.00     | 3       |
| 9     | 1.00      | 1.00   | 1.00     | 2       |

- **Overall Accuracy**: 100.00%
- **Macro Average Precision**: 1.00
- **Macro Average Recall**: 1.00
- **Macro Average F1-Score**: 1.00

These metrics reflect the model's robustness and its capacity to generalize well to unseen data.

## Conclusion

This Digit Recognition System effectively demonstrates the application of GRUs in audio signal processing and achieved a high level of accuracy on both training and testing datasets.
