### How to run the repo
## creat directory
mkdir kyc
cd kyc

## create  virtual environment
python -m venv kyc

## activate th virtual environment
kyc\scripts\activate

## install dependencies
pip install -r requirements.txt

## clonning the repo
git clone https://github.com/cref-y/KYC-AI-Verification.git

## open the kyc_verification.ipynb file
# to execute the cell => shift + return

### alternatives to running teh notebook
# open the notebook from google colab using the link below
# note while using colab change runtime to a temporary gpu for successfull code execution 
https://colab.research.google.com/drive/16C0me9EM92dvp1pJA08zGkhQK6i2V1Is?usp=sharing

### About the notebook
The main aim of the notebook is to extract textual identification information from the uploaded image of identity card

To achieve this the function below are included 


  - extract_text_from_id
  this function extract text from the image including name, identifaction number,country  and serial number from the id image


  - extract_face_from_id
  this function extract the face from the image pring on the id which is later used to find similarity with the image which would later be uploaded.


  - js_to_image,take_photo 
  the combination of this function helps the colab notebook to have accessibility to the camera of the device and allow images to be captured
  
   
   -capture_live_face 
   this functions runs when the camera is on and invokes a face_recognition module which will detect presence of a face within the camera view

   - preprocess face 
   performs featue extraction for both images

  - histogram similarity,compare faces
  this function idetifies similarities between the uploaded image and the face captured by the camera 

  - kyc verification 
  function combines all the above function to perform the  necessary operation on the uploaded data
  expected return type is a dictionary with the extracted text and the similarity score obtained during  face comparison

## Algorithm


The notebook applies the structured similarity model from skimage.metrics module which is a sigmoid function and trys to establish similar structure between images, the algorith rated in a range of 0 to 1 whereby  approachin to 1 indicates the compared images are more similar.
