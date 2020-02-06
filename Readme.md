# Project: Build a Traffic Sign Recognition Program

## Step 0: Load The Data

- The downloaded data set is serialized with pickl, so pickle is used to read it.

## Step 1: Dataset Summary & Exploration

The pickled data is a dictionary with 4 key/value pairs:

- `'features'` is a 4D array containing raw pixel data of the traffic sign images, (num examples, width, height, channels).
- `'labels'` is a 1D array containing the label/class id of the traffic sign. The file `signnames.csv` contains id -> name mappings for each id.
- `'sizes'` is a list containing tuples, (width, height) representing the original width and height the image.
- `'coords'` is a list containing tuples, (x1, y1, x2, y2) representing coordinates of a bounding box around the sign in the image. 
##THE TRAINING, VERIFICATION,AND TEST SETS EACH HAVE 34799,4410 AND 12630 PICTURES,ALL OF WHICH ARE (32,32,3),WITH A TOTAL OF 43 CATEGORIES.##  

## Step2:Design and Test a Model Architecture

### Model 1
convolution 1: 32x32x1  -> 28x28x12 -> relu -> 14x14x12 (pooling)  
convolution 2: 14x14x12 -> 10x10x25 -> relu -> 5x5x25   (pooling)  
flatten: 5x5x25   -> 625  
drop out: 625      -> 625  
linear: 625      -> 300  
linear: 300      -> 100  
linear: 100      -> 43  
After 10 training sessions, a model of traffic sign recognition classifier was obtained. The accuracy rate of training set was 0.998. The accuracy rate on the verification set was 0.929. The accuracy on the test set was 0.933.

### Model 2
Some parameter adjustments were made to model 1  
convolution 1: 32x32x1  -> 28x28x12 -> relu -> 14x14x12 (pooling)  
convolution 2: 14x14x12 -> 10x10x25 -> relu -> 5x5x25   (pooling)  
flatten: 5x5x25   -> 625  
drop out: 625      -> 625  
linear: 625      -> 400  
linear: 400      -> 200  
linear: 200      -> 43  
After 10 training sessions, another model of the traffic sign recognition classifier was obtained. The accuracy rate of training set is 0.999. The accuracy rate on the verification set is 0.945. The accuracy on the test set was 0.943. Compared with model 1, the accuracy is improved and the effect is better.