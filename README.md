<h2>SIGN LANGUAGE TO SPEECH</h2><br>
<p>This project has two main parts the:</p>
<p>1. The Sign Language Recognition Model </p>
<p>2. The Android App</p>

<h3>MODEL:</h3>
<p>Keras deep learning framework on a tensorflow backend is used to build the model

<p>Tiny YOLO was chosen for this project because its light weight and runs on android very well</p>
<p>Future implementations will include SSD on mobilenet to increase accuracy</p>

<p>We'll be moving through building the YOLOv3 network in the python notebook for learning purposes</p>
<p><a href="https://pjreddie.com/darknet/yolo/"> Original Yolo website</a></p>
<p>Model and code inspired by this repo https://github.com/experiencor/keras-yolo2</p>
<p> A good intro to single pass object detection methods here https://www.jeremyjordan.me/object-detection-one-stage/</p>

NOTE: This is a work in progress not yet ready for deployment will update
<h3> ANDROID APP:</h3>
<p>For deployment on android we'll be using Tiny yolo as it's light weight and very fast and runs on many devices but there's a tradeoff in accuracy and we'll use as a demo app</p>
<p>For production we'll be using SSD on mobilenet which should bump up the accuracy by a good factor</p>
<p> Will add a more comprehensive notebook explaing the model training process</p>
<p>The configuration file is a json file, which looks like this:
This is used to set the training parameters, the file names will be replaced with the dataset for the project.
Anchors will be generated for dataset using gen_anchors.py</p>
<br/>```python
{
    "model" : {
        "architecture":  "Tiny Yolo" 
        "input_size":           416,
        "anchors":              [0.57273, 0.677385, 1.87446, 2.06253, 3.33843, 5.47434, 7.88282, 3.52778, 9.77052, 9.16828],
        "max_box_per_image":    10,        
        "labels":               ["raccoon"]
    },

    "train": {
        "train_image_folder":   "/home/andy/data/raccoon_dataset/images/",
        "train_annot_folder":   "/home/andy/data/raccoon_dataset/anns/",      
        "train_times":          10,             # the number of time to cycle through the training set, useful for small datasets
        "pretrained_weights":   "",             # specify the path of the pretrained weights, but it's fine to start from scratch
        "batch_size":           16,             # the number of images to read in each batch
        "learning_rate":        1e-4,           # the base learning rate of the default Adam rate scheduler
        "nb_epoch":             50,             # number of epoches
        "warmup_epochs":        3,              # the number of initial epochs during which the sizes of the 5 boxes in each cell is forced to match the sizes of the 5 anchors, this trick seems to improve precision emperically

        "object_scale":         5.0 ,           # determine how much to penalize wrong prediction of confidence of object predictors
        "no_object_scale":      1.0,            # determine how much to penalize wrong prediction of confidence of non-object predictors
        "coord_scale":          1.0,            # determine how much to penalize wrong position and size predictions (x, y, w, h)
        "class_scale":          1.0,            # determine how much to penalize wrong class prediction

        "debug":                true            # turn on/off the line that prints current confidence, position, size, class losses and recall
    },

    "valid": {
        "valid_image_folder":   "",
        "valid_annot_folder":   "",

        "valid_times":          1
    }
}

```
