# Project
Road Extraction from Satellite Images
# Road Network Extraction from Satellite Imagery

## Objective
Develop a machine learning model to automatically extract road networks from satellite images.

## Dataset
The dataset includes:
- **Training Data**: 6226 RGB satellite images, each of size 1024x1024 pixels. Collected by DigitalGlobe's satellite at a resolution of 50cm per pixel.
- **Validation Data**: 1243 images.
- **Test Data**: 1101 images (without masks).

Labels:
- Each satellite image is paired with a mask image that labels road pixels.
- The mask is a grayscale image where:
  - White (255) represents road pixels.
  - Black (0) represents the background.
- The mask values might not be exactly 0 and 255. Binarize the mask images at a threshold of 128.
- Labels are not perfect and may be less accurate in rural areas. Small roads within farmlands are intentionally unannotated.

## Files
- `train.zip`: Contains training images (a mix of masked and unmasked images).
- `test.zip`: Contains test images.
- `valid.zip`: Contains validation images (no mask images present).
- `class_dict.csv`: Contains class names and corresponding RGB values.
- `meta_data.csv`: Metadata for the images, including paths to satellite and mask images.

## Directory Structure
/content/data
├── train
│ ├── images
│ └── masks
├── valid
│ └── images
├── test
│ └── images


**--Steps--**

## Preprocessing
- Separate masked and unmasked images in the training set.
- Binarize mask images at a threshold of 128.

## Model
- The model used for this task is U-Net, a convolutional neural network designed for biomedical image segmentation.

## Training
- Train the U-Net model on the training set.
- Validate the model on the validation set.

## Testing
- Apply the trained model to the test set to predict road networks.

## Authors
-Isha
