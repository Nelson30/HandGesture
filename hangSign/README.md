Steps:

## Requirements
0. Python 3.x
1. <a href="https://tensorflow.org">Tensorflow 1.5</a>
2. <a href="https://keras.io">Keras</a>
3. OpenCV 3.4
4. h5py
5. pyttsx3

## Installing the requirements
1.pip install -r requirements_gpu.txt

### Creating a gesture
  1. First set your hand histogram. You do not need to do it again if you have already done it. But you do need to do it if the lighting conditions change. To do so type the command given below and follow the instructions below.
    
    python set_hand_hist.py

  * A windows "Set hand histogram" will appear.
  * "Set hand histogram" will have 50 squares (5x10).
  * Put your hand in those squares. Make sure your hand covers all the squares.
  * Press 'c'. 1 other window will appear "Thresh".
  * On pressing 'c' only white patches corresponding to the parts of the image which has your skin color should appear on the "Thresh" window. 
  * Make sure all the squares are covered by your hand.
  * In case you are not successful then move your hand a little bit and press 'c' again. Repeat this until you get a good histogram.
  * After you get a good histogram press 's' to save the histogram. All the windows close.
  
  2. I already have added 26 (0-26) gestures. It is on you if you want to add even more gestures or replace my gestures. Hence this step is <b>OPTIONAL</b>. To create your own gestures or replace my gestures do the following. It is done by the command given below. On starting executing this program, you will have to enter the gesture number and gesture name/text. Then an OpenCV window called "Capturing gestures" which will appear. In the webcam feed you will see a green window (inside which you will have to do your gesture) and a counter that counts the number of pictures stored.

    python create_gestures.py   

  3. Press 'c' when you are ready with your gesture. Capturing gesture will begin after a few seconds. Move your hand a little bit here and there. You can pause capturing by pressing 'c' and resume it by pressing 'c'. Capturing resumes after a few secondAfter the counter reaches 1200 the window will close automatically.

  After capturing all the gestures you can flip the images using

    python flip_images.py

  4. When you are done adding new gestures run the load_images.py file once. You do not need to run this file again until and unless you add a new gesture.
    
    python load_images.py

### Displaying all gestures
  1. To see all the gestures that are stored in 'gestures/' folder run this command
    
    python display_all_gestures.py

### Training a model
1. So training can be done with either Tensorflow or Keras. If you want to train using Tensorflow then run the cnn_tf.py file. If you want to train using Keras then use the cnn_keras.py file.
  
    python cnn_tf.py
    python cnn_keras.py

2. If you use Tensorflow you will have the checkpoints and the metagraph file in the tmp/cnn_model3 folder.
3. If you use Keras you will have the model in the root directory by the name cnn_model_keras2.h5.

You do not need to retrain your model every time. In case you added or removed a gesture then you need to retrain it.

### Testing gestures
   1. First set your hand histogram. 0.
    
    python set_hand_hist.py

  * A windows "Set hand histogram" will appear.
  * "Set hand histogram" will have 50 squares (5x10).
  * Put your hand in those squares. Make sure your hand covers all the squares.
  * Press 'c'. 1 other window will appear "Thresh".
  * On pressing 'c' only white patches corresponding to the parts of the image which has your skin color should appear on the "Thresh" window. 
  * Make sure all the squares are covered by your hand.
  * In case you are not successful then move your hand a little bit and press 'c' again. Repeat this until you get a good histogram.
  * After you get a good histogram press 's' to save the histogram. All the windows close.
  2. For recognition start the recognize_gesture.py file.

    python recognize_gesture.py
3. You will have a small green box inside which you need to do your gestures.

### Using fun_util.py
Here is where you will have all the fun. 
  1. First set your hand histogram. You do not need to do it again if you have already done it. But you do need to do it if the lighting conditions change. To do so type the command given below and follow the instructions below.
    
    python set_hand_hist.py

  * A windows "Set hand histogram" will appear.
  * "Set hand histogram" will have 50 squares (5x10).
  * Put your hand in those squares.
  * Press 'c'. 2 other windows will appear. "res" and "Thresh".
  * On pressing 'c' only the parts of the image which has your skin color should appear on the "res" window. White patches corresponding to this should appear on the "Thresh" window. 
  * In case you are not successful then move your hand a little bit and press 'c' again. Repeat this until you get a good histogram.
  * After you get a good histogram press 's' to save the histogram. All the windows close.
  
  2. Start the file.
  
    python fun_util.py

#### Text Mode (Press 't' to go to text mode)
1. In text mode you can create your own words using fingerspellings or use the predefined gestures.
2. The text on screen will be converted to speech on removing your hand from the green box
3. Make sure you keep the same gesture on the green box for 15 frames or else the gesture will not be converted to text.

