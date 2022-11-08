# Food_Detection_Gradle_Projecct
Deployment of Android application using gradle


Clone this repository in your device

Steps for deployment:

1. Open Android studio and select File>New>import project. then select this directory FoodAI>FoodAI.
2. Once the project loads, configure an emulator and click run.

It detects images of foods and let's you know what type of food it is. Once the picture is taken it will give the details about that food.

## Overview
This demo app allows users to quickly obtain calorie information using their camera. The object detection model utilizes a **[MobileNetV2 SSD](https://github.com/tensorflow/models/tree/master/research/object_detection)** architecture that was trained using transfer learning on 15 unique food classes from the **[Open Images v4](https://storage.googleapis.com/openimages/web/factsfigures_v4.html)** dataset. 

Note: this app was built and modified from the **[TensorFlow Lite Object Detection Android Demo](https://github.com/tensorflow/examples/tree/d0046f3f18c66634395819a50ea6bda65f8bd0ac/lite/examples/object_detection/android)**.


## Model training
* Create a directory in Google Drive called `food_detection`.

* Add the **[training dataset](https://drive.google.com/file/d/11WC6XPp4kHGN1vEzl_ZRnFla99pxIs33/view?usp=sharing)** and **[label_map.pbtxt](https://github.com/jonathanyin12/Food.AI/blob/master/label_map.pbtxt)** to `food_detection`.

* Open `FoodAI_train.ipynb` and follow the notebook instructions.

* To use the newly trained model, download `food_detect.tflite` from `model_checkpoints/tflite_model/` and move it to the _assets_ folder in Android Studio. It should replace the existing pretrained model.

#### Training the model
* When generating the TFRecords, set the flags to point to the location of the dataset. 

* Edit the number of classes in the model configuration file (`s = re.sub('90', 'NUM_CUSTOM_CLASSES', s)`).

#### Adding the model to Android Studio
* Download `food_detect.tflite` from `model_checkpoints/tflite_model/` and move it to the _assets_ folder in Android Studio. It should replace the existing pretrained model.

* Modify `food_labelmap.txt` accordingly. Make sure to keep `???` as the first line.

* Modify `calorie_info.txt` to reflect the custom classes
