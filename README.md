# Age_Detection_OpenCV
CNN Model to detect Age from camera using OpenCV

### DataSet
UTKFace Dataset has more than 20k images with all age groups. Here we have used 11.9K cropped images with 200x200 resolution. 
Here is the link to the dataset- https://susanqq.github.io/UTKFace/

### Labels
The labels of each face image is embedded in the file name, formated like [age]_[gender]_[race]_[date&time].jpg
<div>Total input images: 11960</div>
<div>Total labels: 117</div>
<div></div>
<div>[age] is an integer from 0 to 116, indicating the age</div>
<div>[gender] is either 0 (male) or 1 (female)</div>
<div>[race] is an integer from 0 to 4, denoting White, Black, Asian, Indian, and Others (like Hispanic, Latino, Middle Eastern).</div>
<div>[date&time] is in the format of yyyymmddHHMMSSFFF, showing the date and time an image was collected to UTKFace.</div>

## Data Preprocessing

1. Labels are seperated using split method and and stored as columns in a dataframe named df.
![df](https://github.com/AvantiBuche/Age_Detection_OpenCV/assets/127451991/e2e4ccc7-4c24-48f9-a6fb-b82ebd85489b)
![df1](https://github.com/AvantiBuche/Age_Detection_OpenCV/assets/127451991/eb1e54f3-0195-41da-9fa9-965d55755346)

2. Each images are convered to array format and normalized values between 0-1.
3. shape of images are (11960, 150, 150, 3)
4. Convert labels to one-hot encoded vectors

## Model

1. Activation function = softmax
2. Optimizer = adam
3. Loss function = categorical_crossentropy
4. Batch Size = 100
5. Epochs = 10
6. Loss: 0.3510
7. Accuracy: 0.9178

##OpenCV 

Here video frames will act as inputs in the model to display the age of the face. 

