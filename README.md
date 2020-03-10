# Assignment-Liscense-Plate-Detector
License Plate detector detects license plates in videos and pictures, breaks down the characters, trains the model and predicts the characters as per its training set.
### Steps:
#### 1. Detection:
We have taken two videos of two cars and the detector has detected the placement of the license plate.
![For Video 1](https://user-images.githubusercontent.com/59164181/76335337-2e926d80-6316-11ea-974c-54f78baa4f2e.PNG)
![For Video 2](https://user-images.githubusercontent.com/59164181/76335534-7fa26180-6316-11ea-810c-6b912ff59922.png)
#### 2.Segmentation:
Characters of the license plates broken down:
![Video 1](https://user-images.githubusercontent.com/59164181/76335742-ca23de00-6316-11ea-9673-f9add72d9128.png)
![Video 2](https://user-images.githubusercontent.com/59164181/76335747-cc863800-6316-11ea-9749-2b9348f1ec63.png)
#### 3.Training:
![Video 1](https://user-images.githubusercontent.com/59164181/76335858-f2abd800-6316-11ea-9b4d-dfa29750cb42.PNG)
_Video 1_
![Video 2](https://user-images.githubusercontent.com/59164181/76335847-efb0e780-6316-11ea-9a5f-6d7e93d8f4b7.png)
_Video 2_
#### 4.Detection:
![Video 1](https://user-images.githubusercontent.com/59164181/76336092-4d453400-6317-11ea-83a4-ad85c002a044.PNG)
![Video 2](https://user-images.githubusercontent.com/59164181/76336089-4cac9d80-6317-11ea-88cc-89240d5b77d6.PNG)

### How it works:
The base of our idea is to segment the license images by Connected Component Analysis. Connected regions in the image imply that all linked pixels belong to the same object. 
A pixel is said to be connected to another if they both have the same value and are adjacent to each other.
1.	Car Image 
2.	Grayscale Image 
3.	Binary Image
4.	Applying CCA to get connected regions 
5.	Detect license plate out of all connected regions 
Output of first step is a license plate image detected in a car image. This is provided as input to step2 and CCA is applied on this image to bound the characters in plate. Each character identified is attached into a list.
Model is trained using SVC (4 cross fold validation) with dataset present in directory train20X20. The model is saved as finalized_model.sav which is then loaded to predict each character.


Once the characters of plate are obtained and model is trained, the model is loaded in order to predict each character.
