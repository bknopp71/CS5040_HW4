# Silver Detection Machine Learning Project
## Overview
This dataset was created to support research and educational applications in machine learning–based mineral classification, specifically the detection of silver-bearing minerals from photographic images. It originally consisted of **3,869 silver images** and **16,695 non-silver images**, for a total of **20,564 images** in the initial downloaded dataset. However, due to mislabeled images and class imbalance, the dataset was filtered to **3,655 silver images** and **3,655 non-silver images**, resulting in a balanced total of **7,310 images**.

This repository is organized into three folders: **data**, **metadata**, and **code_file**, which support the dataset used to train machine learning binary classification models for silver detection. The data folder contains all mineral images in JPEG format, the metadata folder stores descriptive information for each image in both CSV and JSON formats, and the code_file folder includes the Python scripts used to collect and process the dataset. The code files also contain exploratory machine learning models using convolutional neural networks and vision transformer architectures.

All images were obtained from the Mindat database, a resource specializing in mineralogical information, and are used solely for educational purposes [1]. The folder structure is outlined below.<br><br>

<img width="282" height="231" alt="image" src="https://github.com/user-attachments/assets/c2c94922-4b66-45d3-a374-4b0d28bb5c63" />

## code_file
This project uses 5 Jupyter Notebooks to implement the data collection, validation, machine learning workflow for the silver detection dataset.

1. ***create_data.ipynb***

This notebook performs automated data acquisition to produce images for the silver and non-silver classes. It reads the Mindat image URL list, filters minerals into silver and non-silver categories, and programmatically downloads available JPEG images. The script includes error handling, logging, and class-balancing logic, including hard and easy negatives, to construct the final dataset.

2. ***data_exploration.ipynb***

This code explores the silver and non silver dataset by generating distribution plots that show class balance, mineral types, and image characteristics such as width, aspect ratio, brightness, and contrast. It then prepares the dataset for machine learning by loading and formatting the images in Keras for CNN training.

3. ***machine_learning_models.ipynb***

This notebook applies five machine learning models to classify mineral images as silver or non silver using balanced datasets and structured preprocessing. The models include three CNN architectures, which are ResNet 50, DenseNet 121, and EfficientNet B0. They also include two transformer models, which are ViT Base Patch16 224 and DeiT Small Patch16 224. Each model is fine tuned and evaluated using standard metrics with threshold optimization to improve overall performance and maximize silver detection. The results are presented with graphs and performance metrics to support clear interpretation and comparison of model behavior.

4. ***metadata.ipynb***

This code builds and validates metadata for silver and non silver image datasets for machine learning models. It verifies files and extracts image metadata such as format, size, color mode, dimensions, and aspect ratio. All metadata is organized and exported to JSON and CSV formats for dataset validation and machine learning use.

5. ***utility_JSON_conversion.ipynb***

This notebook a conversion function use to generate a JSON file from CSV file.

## Data
Images were collected from the Mindat.org database and organized into two binary classes for classification: silver and non silver. The silver_images folder contains 3,869 JPEG images, and the non_silver_images folder contains 16,695 JPEG images. All image data are stored on Google OneDrive, and the data folder provides a direct link from the README.md file. The folder structure of Google OneDrive is shown below. Two versions of the dataset are provided. The first is the original downloaded dataset. The second is a cleaned and balanced dataset prepared for machine learning.

### Orginal Silver Image Dataset
<img width="517" height="258" alt="image" src="https://github.com/user-attachments/assets/fa95db72-092e-425e-aef7-c81316a17889" /> <br>

### Cleaned and Balanced Silver Mineral Image Dataset
<img width="612" height="245" alt="image" src="https://github.com/user-attachments/assets/1fea60e0-42f7-4296-9766-63cd80de31ac" /> <br>


The silver class includes native silver and related silver bearing minerals identified using specific keywords as shown below. The image distribution is not listed here but is included in the exploratory analysis code file.

- *Silver*
- *Argentum*
- *Argentite*
- *Chlorargyrite*
- *Chalcopyrite*
- *Proustite*
- *Pyrargyrite*
- *Stephanite*
- *Polybasite*
- *Pearceite*
- *Miargyrite*
- *Freibergite*

The non silver class is composed of approximately 70% hard negative images and 30% easy negative images to improve model robustness. Hard negatives include the minerals listed below, and easy negatives include all minerals that are neither hard negatives nor silver bearing.

- *Galena*
- *Pyrite*
- *Hematite*
- *Graphite*
- *Stibnite*
- *Chalcopyrite*
- *Molybdenite*

Each image has corresponding metadata that provides a class label of 1 for silver and 0 for non silver, along with the associated mineral name, which can be used directly in machine learning classification models. Each dataset has its own metadata file for the silver and non silver classes.

## Metadata
All image classes have metadata stored in both CSV and JSON formats. The files are identical in content and follow the same labeling scheme. Each image has an associated set of metadata fields, as shown below.

<p align="left"> <img width="566" height="295" alt="image" src="https://github.com/user-attachments/assets/28f7c591-84c3-4af7-a736-714f61754659" /> </p>

Both formats store corresponding image data, where element 0 represents image_0 and element 1 represents image_1, continuing sequentially through the dataset. Metadata for silver images is stored in silver_metadata.csv and silver_metadata.json, while metadata for non-silver images is stored in non_silver_metadata.csv and non_silver_metadata.json. The `metadata/` folder contains structured information for all images in both the original and cleaned datasets. It is organized into two subfolders: <br><br>
<img width="335" height="263" alt="image" src="https://github.com/user-attachments/assets/d463924d-f703-4afc-9d2c-1edb6c93d1d8" />
- **original_dataset/**  
  Contains metadata for the initial unprocessed dataset. This dataset is unbalanced and includes all downloaded images prior to filtering. Metadata files provide class labels, mineral names, and image attributes, and may include inconsistencies due to mislabeled or corrupted data.

- **cleaned_dataset/**  
  Contains metadata for the processed and balanced dataset used for machine learning. This dataset has been cleaned to remove invalid samples and adjusted to achieve a balanced distribution between silver and non-silver classes. Metadata includes labels and additional image features used for model training.

- **README.md**  
  Provides documentation describing the metadata structure, file formats, and dataset organization.



## Reference
[1] Hudson Institute of Mineralogy, “Mindat.org – The Mineral Database.” [Online]. Available: https://www.mindat.org. Accessed: Feb. 14, 2026.

## Author
Brent Knopp<br>
Computer Science, Data Science Program<br>
University of Idaho<br>
Coeur d'Alene, Idaho<br>
Email: knop8939@vandals.uidaho.edu
