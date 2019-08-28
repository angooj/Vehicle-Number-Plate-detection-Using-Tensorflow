# Vehicle-Number-Plate-detection-Using-Tensorflow

## Categoty - Object detection & OCR
### We have to identify the license place in the image provided and do an OCR to extract the characters from the detected license plate.
#### The project developed using TensorFlow to detect the License Plate from a car and uses the Tesseract Engine to recognize the charactes from the detected plate.
* Dataset given in [**Indian_Number_plates.json file**](Indian_Number_plates.json)
* To see the results open [**OCR_detected_license_plate_using_Tensorflow.ipynb file**](OCR_detected_license_plate_using_Tensorflow.ipynb)

### Software Packs Needed
* Anaconda 3 (Tool comes with most of the required python packages along with python3 & spyder IDE)
* Tesseract Engine (Must need to be installed)

### Python Packages Needed
* Tensorflow
* openCV
* pytesseract
* labelImg

### TRAINING PHASE -- IMAGE LABELING
* Collected the set of images (Cars along with number plate) from the sources such as Google Images and Flickr. Then annotated the set of images by drawing the boundary box over the number plates to send it for the training phase.
  * The Annoation gives the co-ordinates of license plates such as (xmin, ymin, xmax, ymax)
  *Then the co-ordinates are saved into a XML file
  * All the XML files are grouped and the Co-ordinates are saved in CSV file.
  * Then the CSV file is converted into TensorFlow record format.
* The set of other separate 15 images also gone through the above steps and saved as Test Record file
* <img src="/doc/img1.PNG" alt="My cool logo"/>

### GPU TRAINING
* By using the Tensorflow-gpu version, the set of annotated images were sent into the Convolutional neural network called as ssd-mobilenet where the metrics such as model learning rate, batch of images sent into the network and evaluation configurations were set. The training phase of the model took several days. At last the model came around with the positive result and detected the number plate over the input images.

### OCR PART
* Then the detected number plate is cropped using Tensorflow, By using the Google Tesseract-OCR (Package originally developed to scan hard copy documents to filter out the characters from it) the picture undergoes some coversions using computer vision package then the charcters are filtered out.
* <img src="/doc/img2.PNG" alt="My cool logo"/>

