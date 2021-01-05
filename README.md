# ASLclassifier
*Built by Spencer Ball, November 2020

## What is it?
A convolutional neural network which classifies 56x56 pixel images of American Sign Language letters into their English letter equivalents.

## Results
88.1% Validation Accuracy achieved. For confusion matrix and accuracy/loss plots see output at bottom of the notebook file.

## What's in ASLclassifier.ipynb?
Image normalization, input dataset structuring (torch DataLoader creation), CNN model definition and instantiation, full training loop, and model performance visualization.

## Hyperparameter choices
The 6 first hyperparameters at the top of the file were optimized through a grid search.

## What I learned
Batch normalization allows for a more accurate loss calculation and backwards step by effectively separating the training of each fully connected layer. This phenomenon is evident because when batch normalization is used, training time to reach a given validation accuracy is reduced and maximum achievable validation accuracy rises. Additionally, I found using cross-entropy loss instead of mean-sqaured-error loss sped up the training process considerably. Specifically, with CELoss, ~70% validation accuracy is achieved in 3 epochs, whereas reaching this accuracy would take 5 or 6 epochs using MSELoss. This is likely because the cross entropy loss function grows very quickly as the trainable parameters move in the wrong direction.
