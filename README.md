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

NOTE: This is a work in progress not yet ready for deployment will update
<h3> ANDROID APP:</h3>
<p>For deployment on android we'll be using Tiny yolo as it's light weight and very fast and runs on many devices but there's a tradeoff in accuracy and we'll use as a demo app</p>
<p>For production we'll be using SSD on mobilenet which should bump up the accuracy by a good factor</p>
