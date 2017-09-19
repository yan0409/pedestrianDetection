# Pedestrian Detection
## Neural Network with Sliding Window Image Pyramid

Program to detect and classify pedestrians from an image. Acheived using 1 layer, 150 hidden unit neural network trained on the [Daimler dataset](http://www.gavrila.net/Datasets/Daimler_Pedestrian_Benchmark_D/Daimler_Pedestrian_Segmentatio/daimler_pedestrian_segmentatio.html) which was border-reduced; the adjusted data is included [here](https://github.com/rachelang/pedestrianDetection/tree/master/data). After training the classifier, I used the sliding window image pyramid method to scan test images, where positive areas would be marked with a bounding box as shown [below](#results). Currently my program will produce multiple bounding boxes in areas of interest, so the next step will be to merge them to produce a clear, precise detection result.

## Challenges
I attempted to use a multiclass approach to train the network, but because of the massive variety in non-positive data (many variety in backgrounds) and the lack of negatvie data, a multiclass approach was producing too many false positives. That experiment can be found [here](https://github.com/rachelang/pedestrianDetection-variationMultiClass). To overcome this, I then switched back to having a single output unit in the network, and used a very high prediction threshold (h >= 0.90 to 0.95) to increase precision and obtain the results shown.

<a name="results"></a>
## Results
Close up of two people        |  Multiple huddled people
:----------------------------:|:-------------------------:
![closeUp](https://github.com/rachelang/pedestrianDetection/blob/master/borderedImages/closeUp.PNG) | ![closeUpDifferentDistance](https://github.com/rachelang/pedestrianDetection/blob/master/borderedImages/closeUpDifferentDistance.png)

Multiple people at different distances |  Multiple in-line people
:-------------------------------------:|:-------------------------:
![differentDistance](https://github.com/rachelang/pedestrianDetection/blob/master/borderedImages/differentDistance.jpg) | ![inLine](https://github.com/rachelang/pedestrianDetection/blob/master/borderedImages/inLine.png)

Single person       |  Multiple people at a distance
:------------------:|:-------------------------:
![onePersonLightBackground](https://github.com/rachelang/pedestrianDetection/blob/master/borderedImages/onePersonLightBackground.PNG) | ![multiplePeople](https://github.com/rachelang/pedestrianDetection/blob/master/borderedImages/multiplePeople.PNG)
