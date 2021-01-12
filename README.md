# Auto Face morphing

## Organization

- face_detection folder contains the training codes and codes for creating the final composite

- inside face_detection folder
  - dataset.py is for custom PyTorch dataset and transforms
  - util.py is for utility functions such as plotting and coordinates transformation
  - train_key_points_detection contains training code, morphing code and codes for final composite
  - EPOCH_48_BATCH_98.pth is our trained model for keypoints detection
  - /ori_images contains all the images downloaded from web
  - /cartoon_images contains all the cartoonized version of original images

## Usage

- Train Your Own Model

  - Open train_key_points_detection.ipynb in Google Colab, run the code until "Eval trained model section"
  - The models during training will be automatically saved in "content/model" folder

- Evaluate Your Model on Test Images
  
  - Open train_key_points_detection.ipynb in Google Colab, follow the instruction of "Eval trained model section"
  - It will download an image from web and transform it to an accepted form of the nerual network
  - Finally, it will plot the image along with the key points detected

- Create your own gifs
  - Put your images in folder 'face_detection/original_img'
  - Run the Cartoonization part (if the tensorflow cannot be imported, just restart the kernel, uninstall the tensorflow, and rerun all the cells beginning from Evaluation part)
  - Run the generation cell of the gif and it would be saved in 'Drive'

## Some Explanations

- This is an implementation of Project 4 of CS194-26 in UC-Berkeley (<https://inst.eecs.berkeley.edu/~cs194-26/fa20/hw/proj4/>)
- The data is from Kaggle (<https://www.kaggle.com/c/cs194-26-fa20-proj4>)
- There are 6666 images in total. However, after examnation, half of the images are mirror version of the other half (In other words, no need to horizontal flip)
- Model used is ResNet18

## Possible Improvements

- More transformers such as ColorJitter, translation etc
- Implementation of early stopping technique to avoid overfitting
