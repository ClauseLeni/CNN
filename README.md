# CNN for Predicting PPR Protein Binding Sites

## Investigators: Leni Campbell-Clause, Ian Small, Catherine Colas des Francs-Small

## Overview
This repository contains code for training and using a Convolutional Neural Network (CNN) to predict Pentatricopeptide Repeat (PPR) protein binding sites in plant organelles. The CNN is trained on four data types: small RNA (sRNA), 3' and 5' transcript ends, and conservation scores for "known" PPR binding sites. The trained model can then be used to predict the locations of potential PPR binding sites based on the patterns observed in the training data.

## Data
The input data for training the CNN includes:
- Small RNAseq
- Transcript end RNAseq (3' and 5')
- Conservation scores

## Training
To train the CNN, follow these steps:

1. Preprocess the input data by calculating sRNA depth, 3' and 5' transcript end position counts, and conservation scores. 
2. Generate training footprints with defining_3layer_footprints.ipynb
3. Run the fiveprime and threeprime CNNs seperately
4. Three CNN network structures are provided
5. Define the architecture of the CNN model using Flux.jl
6. Specify the hyperparameters for training, such as learning rate and batch size.
7. Train the model
8. Test the model

## Usage
Once the CNN is trained, you can use it to make predictions on "new" PPR protein binding sites:

1. Feed the preprocessed data into the trained CNN model.
2. Obtain predictions from the CNN, indicating the likelihood of PPR protein binding at different window positions of the organelle genome.
3. Distil the predictions with distil.ipynb
