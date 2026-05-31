# Remote sensing for landcover detection: ML techniques

This repository contain course material for the MLESS lecture by Prof. Dr. Martin Schultz at the University of Cologne, Germany.
Two Jupyter notebooks demonstrate the use of random forests and convolutional neural networks for a simplified landcover classification task
based on satellite remote sensing data.

The data for these demonstrations is a subset from the [SAT-6](https://csc.lsu.edu/~saikat/deepsat/) dataset by
_Saikat Basu, Sangram Ganguly, Supratik Mukhopadhyay, Robert Dibiano, Manohar Karki and Ramakrishna Nemani, DeepSat - A Learning framework for Satellite Imagery, ACM SIGSPATIAL 2015._
It consists of 28x28 pixels uint8 images with 4 channels and labels of 6 landcover classes - barren land, trees, grassland, roads, buildings and water bodies.

The classification task is scene classification, i.e. the entire 28x28 pixel image is classified a sone landcover type.

## Download the data

Unfortunately, there is no anonymous and free access to the Deepsat data. However, a subset has been extracted and made available atthe B2SHARE server at FZ Jülich: 
https://b2share.eudat.eu/records/89654eac10724d30a6c7e51f2c5422de. Thi scomprises only the test set of the original data - for our educational experiments, this is sufficient.

The three data files must be stored in a `data` directory in the same path as the notebook itself.

## Run the example notebooks

Start with the Random_forest_classifier notebook. WARNING: loading the data into pandas consumes ~5 GBytes of memory. Make sure that your Jupyter lab has sufficient memory.

Once you fully understood what this notebook does, take a look at the CNN_classifier notebook and run it. Note that you need to have Pytorch installed to run the CNN_classifier notebook.

Compare training times, inference times (if you notice a difference) and the quality of the results.

Think about the network and training paraneters: which ones would you modify if you want to improve the results?


## Author

Martin Schultz, April 2026



# Remote Sensing Land Cover Classification

## Author

Fariba Yazdanjooei

## Project Overview

This project investigates land cover classification using remote sensing image data. The aim is to classify satellite image patches into different land cover classes using both classical machine learning and deep learning methods.

Two approaches were used:

* Random Forest Classifier
* Convolutional Neural Network (CNN)

The project also studies how different spectral bands and hyperparameters influence classification performance.

---

## Dataset

The dataset consists of remote sensing image patches with multiple spectral channels. Different channel combinations were tested in order to evaluate their importance for land cover classification.

The experiments include:

* RGB channels
* Red, Green and Near Infrared channels
* Full image input for CNN classification

---

# Random Forest Classifier

## Baseline Model

A Random Forest classifier was trained on the provided remote sensing data. The model was used as a classical machine learning baseline for comparison with the CNN model.

## Classification Accuracy

The Random Forest classifier achieved an accuracy of approximately 0.908 on the test dataset.. The classification report and model accuracy are included in the notebook.

## Correct and Incorrect Classifications

Correctly classified and misclassified examples were visualized in the notebook. This helps to understand where the model performs well and where it makes mistakes.

## RGB-only Experiment

The classifier was trained using only the RGB channels.

This experiment was used to test how well visible color information alone can classify the land cover classes.

## Red-Green-NIR Experiment

The classifier was also trained using the Red, Green and Near Infrared channels.

NIR information is useful for remote sensing tasks, especially for distinguishing vegetation and land cover types.

## Random Forest Hyperparameter Experiment

The hyperparameter `n_estimators` was changed from 100 to 200.

### Expectation

Increasing the number of trees should make the Random Forest model more robust and may improve the classification accuracy.

### Result

### Result

The classification accuracy changed from approximately 0.928 to 0.908 after increasing the number of trees.

### Conclusion

The experiment shows that the performance of a Random Forest classifier depends on the chosen hyperparameters.

---

# Convolutional Neural Network

## CNN Model

A Convolutional Neural Network was implemented and trained on the remote sensing image patches.

The CNN uses convolutional layers to learn spatial image features automatically.
The CNN achieved an accuracy of approximately 0.927 on the test dataset.

## Classification Report

The CNN classification report is included in the notebook. It shows precision, recall and f1-score for the different classes.

## RGB-only CNN Experiment

The CNN was also trained using RGB channels only.

This experiment was used to compare the performance of RGB-only input with the full input data.

## Epoch Hyperparameter Experiment

The number of training epochs was increased from 5 to 10.

### Expectation

Increasing the number of epochs gives the CNN more time to learn features from the training data and may improve the classification accuracy.

### Result

The CNN reached an accuracy of approximately 0.927 after training for 10 epochs.

### Conclusion

Increasing the number of epochs improved the CNN training process in this experiment, although too many epochs could lead to overfitting.

---

# Summary of Experiments

| Experiment                   | Description                                      |
| ---------------------------- | ------------------------------------------------ |
| Random Forest baseline       | Classical machine learning classifier            |
| Random Forest RGB-only       | Classification using RGB channels                |
| Random Forest R-G-NIR        | Classification using Red, Green and NIR channels |
| Random Forest hyperparameter | `n_estimators` changed from 100 to 200           |
| CNN baseline                 | Deep learning classifier                         |
| CNN RGB-only                 | CNN trained with RGB input                       |
| CNN epoch experiment         | Epochs changed from 5 to 10                      |

---

# Conclusion

Both Random Forest and CNN models were able to classify land cover types from remote sensing image data.

The experiments show that:

* Spectral band selection affects classification performance.
* NIR information is useful for remote sensing classification.
* Random Forest performance depends on hyperparameter choice.
* CNN performance depends on training settings such as the number of epochs.
* CNNs are well suited for image classification because they learn spatial image features automatically.

All code, results and explanations are included in the notebook files in this repository.


