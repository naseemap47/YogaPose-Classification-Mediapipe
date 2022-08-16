# CustomPose-Classification-Mediapipe
Creating a Custom pose classification using Mediapipe with help of OpenCV

## Demo
**(Yoga Poses Dataset)**


Using this Custom Pose Classification I created a Yoga Pose Classification

### 1.Download Dataset: 
```
wget -O yoga_poses.zip http://download.tensorflow.org/data/pose_classification/yoga_poses.zip
```
About Dataset:
- 5 Classes: **Chair, Cobra, Dog, Tree and Warrior**
- Contain Train and Test data
- Combain both Train and Test data

### 2.Create Landmark Dataset for each Classes
```
python3 poseLandmark_csv.py -i <path_to_data_dir> -o <path_to_save_csv>
```
Example:
```
python3 poseLandmark_csv.py -i data/ -o data.csv
```
CSV file will be saved in **<path_to_save_csv>**
### 3.Create DeepLearinng Model to predict Human Pose
```
python3 poseModel.py -i <path_to_save_csv> -o <path_to_save_model>
```
Example:
```
python3 poseModel.py -i data.csv -o model.h5
```
Model will saved in **<path_to_save_model>** and Model Metrics saved in **metrics.png**
### 4.Inference
Show Predicted Pose Class on Test Image
```
python3 inference.py -i <path_to_test_image> -m <path_to_saved_model>
```
Example:
```
python3 inference.py -i data/test/test.jpg -m model.h5
```
**To Exit Window - Press Q-key**

## Custom Pose Classification
```
git checkout custom
```
### 1.Take your Custom Pose Dataset
### 2.Create Landmark Dataset for each Classes
CSV file will be saved in **<path_to_save_csv>**
```
python3 poseLandmark_csv.py -i <path_to_data_dir> -o <path_to_save_csv>
```
### 3.Create DeepLearinng Model to predict Human Pose
Model will saved in **<path_to_save_model>** and Model Metrics saved in **metrics.png**
```
python3 poseModel.py -i <path_to_save_csv> -o <path_to_save_model>
```
### 4.Inference
Open **inference.py**

change **Line-43**: 
According to your Class Names, Write Class Order
```
python3 inference.py -i <path_to_test_image> -m <path_to_saved_model>
```
Show Predicted Pose Class on Test Image

**To Exit Window - Press Q-key**
