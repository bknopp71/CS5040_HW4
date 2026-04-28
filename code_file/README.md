# Python Files Used To Build This Project
This project uses 5 Jupyter Notebooks to implement the data collection, validation, machine learning workflow for the silver detection dataset.

1. ***create_data.ipynb***

This notebook performs automated data acquisition. It reads the Mindat image URL list, filters minerals into silver and non-silver classes, and programmatically downloads available JPEG images. The script includes error handling, logging, and class balancing logic (including hard and easy negatives) to construct the final dataset.

2. ***data_exploration.ipynb***

This code performs exploratory data analysis on the silver and non-silver mineral image dataset by visualizing class distribution mineral types and image characteristics such as width aspect ratio brightness and contrast. It also cleans the dataset filters valid samples and prepares the images for machine learning by loading resizing normalizing and formatting them for CNN training

3. ***machine_learning_models.ipynb***

This notebook applies five machine learning models, including two transformers and three CNNs, to classify mineral images as silver or non-silver. It uses balanced datasets with preprocessing. All models are evaluated using standard machine learning metrics, with threshold optimization applied to maximize recall for the silver class.

4. ***metadata.ipynb***

This notebook validates the downloaded dataset and generates structured metadata. It checks file integrity, extracts image properties (dimensions, size, format), assigns class labels, and exports metadata into CSV and JSON formats. These files are used to link each image to its corresponding data record for machine learning workflows.

5. ***utility_JSON_conversion.ipynb***

This notebook a conversion function use to generate a JSON file from CSV file.

