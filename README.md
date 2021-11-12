AI Face Mask Detector:

Files:
Dataset.zip
face_mask_detector.py
COMP6721-AI-Project-1

Here,
 Dataset.zip contains the dataset used in our project.
 face_mask_detector.py is the main file which runs the program. Here lies the main logic of loading, training images and classifying unlabelled images.
 COMP6721-AI-Project-1 is the file which stores the trained model. Once the model is trained, it is stored on this path.

Face Mask Detection/Datasets -> contains all the images that will be used in training and testing the model.
Face Mask Detection/saved_model -> contains file which stores the trained model. Once the model is trained, it is stored on this path.
Face Mask Detection/loaded_images.npy -> contains the pre-processed loaded images into numpy array format.
Face Mask Dectection/test -> It contains 13 different category images which are used to test the trained model.

Run Program:

 -> Here the main function is FaceMaskDetection().

 -> In FaceMaskDetection(), it will check for "GPU". If there is any GPU available then it will set device to "GPU", otherwise set it to "CPU".

 -> Once the device is selected, data classes(categories) are retreived from dir_path (path to all the sub folders in dataset). 

 -> Then classes obtained are then combined with label with the help of dictionary. This is done in set_labels_and_zip_class_and_label(data_classes), 
    which takes classes as input.

 -> Once the data_classes and labels are zipped, images are being fetched and these images and their labels are appended to an empty list named data. 

 -> All this is done in load_image(data_classes, dir_path, data_labels) method, which takes classes, dir_path and data_labels as input and return data.

 -> The obtained data is then shuffled and then saved into a pre-specified path into dataset. This is accomplished by shuffle_and_save_data(data, save_dir).

 -> Then we pass the pre-specified path where the shuffled data is stored into data_loader() method, which split the dataset into 
    two training and testing dataset and loads the data into these datasets. This method returns two datasets namely training_dataset and testing_dataset.

 -> The next method in queue is to train the training_dataset and testing_dataset. For this, we pass these two datasets and epoch_number 
    into the method called model_trainer(), which return trained model.

 -> Once we have trained model, we save it into our dataset file for future references. 

 -> To find accuracy, f-score, precision, and support and also plot the confusion matrix of the trained models, we used method named generate_matrix() 
    which takes model, name of dataset, train_dataset as input and output the result and a confusion_matrix.

 -> At the end, to predict some image, we use predict_image, which will predict class(category) of specified image. 
 
  
