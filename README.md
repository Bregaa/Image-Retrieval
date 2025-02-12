# Image-Retrieval

## Introduction
This project focuses on image retrieval using two primary approaches: a **Pre-Trained Convolutional Neural Network (CNN)** and a **Siamese Network**. The goal is to retrieve similar images from a dataset of mammals containing 45 categories and 13,751 images. We evaluate the performance of these methods using mainly accuracy, and the Average Normalized Modified Retrieval Rank (ANMRR). Additionally, we explore combining the best-performing methods to reach better overall performance, and the use of relevance feedback to improve drastically the retrieved images of the worst performing categories.

## How to Use

### Setting Up the Environment
1. **Google Colab**: Open the provided notebook in Google Colab. You can place the notebook in any directory within your Colab environment.

2. **Dataset**: 
   - Download the datasets zip files (and all the extensions), extract it and re-zip it with the same name (MammalsDataset.zip), and upload it to the root folder of your Google Drive (`myDrive`). The compressed folder had to be divided to avoid GitHub's 100MB maximum file size.
   - Do not rename the dataset's zip file.

3. **Pre-Computed Models and Extracted Features**:
   - If you want to use pre-computed models and extracted features (suggested), download the "IR Saves" folder and place it in the root folder of your Google Drive (`myDrive`).
   - This folder contains trained models and extracted feature arrays that can be directly used for inference or further analysis.

## Demo
- The demo requires the same setup. 
- Images from the test set are used, some of their indices are suggested at the start of the demo section. The images are then used as queries for the base method, the fine-tuned siamese method and the combined method. Lastly, an example of relevance feedback is provided.

## Results Recap

### Pre-Trained CNN (MobileNetV2)
- **Accuracy**: 86.20%
- **ANMRR**: 0.39

### Siamese Network
- **Accuracy**: 12.14%
- **ANMRR**: 0.88

### Fine-Tuned Siamese Network (MobileNetV2)
- **Accuracy**: 83.80%
- **ANMRR**: 0.40

### Combined Method (combining the first and third method)
- **Accuracy**: 87.09%
- **ANMRR**: 0.39
- 
### Relevance Feedback
To improve the performance of the worst-performing classes (e.g., sea_lion), we implemented **relevance feedback** using the Rocchio Algorithm. This technique adjusts the query based on user feedback, significantly improving retrieval accuracy for challenging classes.

## Conclusion
The combined method, which integrates the strengths of both the Pre-Trained CNN and the Fine-Tuned Siamese Network, provides the best overall performance with an accuracy of 87.09%. This approach slightly improves the retrieval of the worst-performing classes, such as seals, which are often confused with similar animals like sea lions. Further improvements can be explored using relevance feedback techniques to enhance the performance of the worst classes.