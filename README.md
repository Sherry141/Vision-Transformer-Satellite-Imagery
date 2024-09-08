# Vision-Transformer-Satellite-Imagery

## Spatio-temporal Analysis of Satellite Imagery using Siamese Network and Vision Transformers

## Overview

This project focuses on spatio-temporal analysis of satellite imagery to classify land-use transitions, such as construction, deconstruction, cultivation, and decultivation. Using a Siamese network architecture with Vision Transformers (ViT), the model is designed to analyze the changes between satellite images taken at different times.

The dataset used in this project is the C2D2 dataset, consisting of image stacks from three cities: Lahore, Aleppo, and Kathmandu. Each image stack contains three images of a specific location from different years (2011, 2013, and 2017). The model attempts to classify transitions in land use based on these satellite images.

For a comprehensive explanation of the project, including methodologies, results, and reflections, please see the `Final Paper`.

## Files in this Repository

- **`siamese_model.ipynb`**: This notebook contains the implementation of the Siamese network architecture using Vision Transformers (ViT). It covers the training, validation, and testing of the model.
- **`link_to_dataset.txt`**: A text file containing the link to the C2D2 dataset used in the project.
- **`Final Paper.pdf`**: The final report for the project, which includes a detailed explanation of the model architecture, results, and analysis.
- **`stats.docx`**: A document containing the detailed statistics of the model's performance with various configurations during the tuning process.

## Model Architecture

The model utilizes a Siamese network with Vision Transformers (ViT) as its base. The two identical subnetworks in the Siamese architecture process the ‘before’ and ‘after’ satellite images independently, generating embeddings for each. These embeddings are then concatenated and passed through fully connected layers to classify the type of transition in land use.

### Key Features:
- **Siamese Network**: Uses two identical Vision Transformer networks to process pairs of satellite images.
- **Vision Transformer (ViT)**: ViT pretrained on ImageNet is used to generate embeddings from the images.
- **Classification**: The final layer classifies the transitions into four categories: construction, deconstruction, cultivation, and decultivation.

## Model Training

The model was trained using the C2D2 dataset, which contains 1,996 image stacks. The training was done over multiple epochs, with validation and testing performed on unseen data. Early stopping and hyperparameter tuning were applied to reduce overfitting and optimize performance.

Key training metrics:
- **Training accuracy**: 96% 
- **Validation accuracy**: 71%
- **Test accuracy**: 72%

For more detailed metrics, see the `stats.docx` file.

## Dataset

The dataset consists of satellite imagery from the C2D2 dataset, available via the link in the `link_to_dataset.txt` file.

## Future Improvements
Details on future improvements and more analysis is available in `Final Paper.pdf`. In summary: 

- **Triplet Loss**: Exploring triplet loss could help improve the model’s ability to detect specific transitions.
- **Data Quality**: Improving the quality of the satellite images or using multispectral data could enhance classification accuracy.
- **Class Redefinition**: Adjusting the transition classes to more easily distinguish cultivation and decultivation transitions.

## Usage

To run the model:

1. Clone the repository.
2. Install the necessary libraries (TensorFlow, vit-keras, etc.).
3. Load the dataset using the provided link.
4. Place the `siamese_model.ipynb` notebook and the dataset in your Google Drive, and run it. Alternatively, you can run it locally but would have to accordingly change the second block of code in `siamese_model.ipynb`. 