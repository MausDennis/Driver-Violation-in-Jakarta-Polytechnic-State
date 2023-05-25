# Driver-Violation-in-Jakarta-Polytechnic-State
In this era, technology is developing so rapidly. More and more new inventions and technological developments that already exist which have a variety of positive impacts and help overcome problems that are often experienced by humans. In this case, the use of technology is used to take action against motorists who break the rules.

# 1. Planning and Implementation
Four machine learning models were developed, each with special abilities. the capacity to identify a vehicle's type through pictures and videos, determine whether the driver is wearing a helmet, identify a vehicle's license plate and take a photo of it to identify the letters and numbers, and calculate the speed of the driver's car on the highway. This methodology can be used by security forces to evaluate violations that take place in their assigned territory. The talk starts with developing application systems and application programs.

# 2. How the model's works?
The following is a picture of the camera used and installed in a place at the Politeknik Negeri Jakarta

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/WhatsApp%20Image%202023-05-25%20at%2007.03.24.jpeg width="250" height="250">
</p>

Applications programs are demonstrated using flowchart diagrams. Flowchart diagrams in systems illustrate the connection and timing of processes.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-1-page-00001.jpg width="1000" height="500">
</p>

The flowchart above shows how the model determines the classification of tasks to be performed. When the dataset is entered into the model we want to model, the system starts. First, the system identifies the type of vehicle that was at the scene, then identifies the number plate of the vehicle that is crossing the road. Finally, the system evaluates data from cameras at the scene to ascertain whether any violations have occurred, such as exceeding the speed limit for all vehicles and requiring motorists to wear helmets. Each tested model is entered into the system one by one. Then, images from the scene cameras were used to test the model. In the end, the results of the analysis made by the model will be sent in the form of images or videos, depending on how well the model accepts the test object.

# 2.1 Vehicle Type Detection

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-2-page-00001.jpg width="500" height="750">
</p>

The flowchart above shows the process of identifying vehicle types using Google Collaborate. Datasets, institutions, and photo/video input from surveillance cameras will be entered into Google Collaborate.

The callback will be requested after entering those three items. Take the time to customize the directory to ensure that it points to the dataset in question. calling back to ensure that the data to be trained in the future does not exceed 98%. Because, according to the rules of the confusion matrix game, the machine learning model has a tendency to judge the target with the wrong result if the level reaches 98%.

Next, reading and managing the dataset, which means modifying the existing dataset. The dataset is changed to divide the class (vehicle type class) that contains the image. This image is intended to be included as training and validation data. After reading and setting the dataset. Next, the machine learning model will be configured, compiled, and trained. At this point, the convolutional neural network (CNN) architecture will be configured, compilation will be performed, and the model training duration will be set. At the end, the graph shows the results of training the machine learning model.

The graph shows the result of training the machine learning model after that step. To retrain a previously created model, Yolov5 will be called. enter video test model to enter vehicle type detection model analysis and remove requirements.txt to prevent unexpected errors. Lastly, yolov5 downloads the retrained video file.

# 2.2 Helmet Use Detection

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-3-page-00001.jpg width="500" height="750">
</p>

In the flowchart above, the helmet use detection diagram process is explained by two paths: Roboflow and Google Collaboratory. The second path ends when the dataset from roboflow is exported to Google Collaboratory. This continues until the trained weight is used to retrain the machine learning model to find images from various classes (helmet, no_helmet, and no helmet), which the model believes have above 40% correctness.

A. Roboflow
The dataset is currently created on the Roboflow platform. Search for the best dataset from various sources in Roboflow, then annotate the images and create datasets. The dataset will be exported to Google Collaborate using the lines of code generated by Roboflow once everything is complete.

B. Google Collaboratory
Download dependencies at Google Collaboratory, import the library to use, enter the Yolov5 repository, and select the GPU runtime. To support machine learning model requirements, download the dependencies, import the library, and enter yolov5. To increase the ability to perform object detection, enter yolov5.

After the Roboflow path has completed its work, the changed dataset must be exported. The model will be placed in the Yolov5 directory. In this directory, the model is retrained, a model analysis chart is created, and the trained weight is collected. Training weights are used to find files containing previously trained images to be trained again. when finished, train with the body weight trained. Images in a folder will be found and displayed on the screen by models that have a correct confidence level above 40%. Finished

# 2.3 License Plate Reading Detection

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-4-page-00001.jpg width="500" height="750">
</p>

As before, license plate detection and reading uses Kaggle rather than Google Colaboratory. The dataset must be fetched before work begins, which must be integrated with the .xml file. File.xml contains information about bounding box photo coordinates for .jpg and .PNG formats. After the dataset is integrated with the previous file.xml.

Followed by using the Kaggle code editor. in the Kaggle editor code. The Imutils installation has been completed and the necessary library imports have been performed. To support the contour process that will be carried out in the Kaggle code editor, cuteils is installed. In the next step, a route call of the image to be tested is performed.

In order for a license plate detection model to read the writing on a car's license plate, the test requires many steps. Initially, the color of the target image is changed to an overall gray color. Then, the noise filtering and edge detection processes were changed.

In digital images, points where the brightness of the image changes sharply or, more formally, has discontinuities can be identified through an edge detection/edge detection process, which is used to reduce noise. Currently, the canny method is used to detect edges. The Canny method is used because it is capable of detecting far more discontinuities than other edge detection methods, such as the Sobel, Prewit, and Robert methods, all of which are less effective at detecting edges. The target image will have contours and a solid black base color after the edge detection and noise reduction processes are complete. go to the implementation part of contour/contour. Contours or contours can be used to identify contours or contours in the intended image. To find contours that can be detected properly by the system in the target image, use the canny edge detection technique. The output of this process is finding the location of the number plate in the form of a matrix.

Masking and reading of license plates is done afterwards with the help of the easyOCR library. The target image will be masked at the license plate location and designated area. The result is that the target image shows only part of the license plate, with the color around it being black. After obtaining a picture of the number plate, the system is asked to show the results by displaying a picture of the plate showing the number plate. After that, the image of the slice is given an overall gray color. Slice images are grayed out throughout to help the easyOCR library read and provide reading results. After getting the number plate reading results, the display will return to the image in question, but with the bounding box and the number plate reading results appearing in the image in question.

# 2.4  Driver speed detection

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-5-page-00001.jpg width="500" height="750">
</p>

Driver speed detection is similar to detecting a driver's license plate number on Kaggle. The coding process in this section requires input such as installing the ubuntu package (libgtk2.0 – dev), importing the required libraries, test videos, and cascade. However, Cascade is a video file with a bounding box. This derived file is coded.xml.

The code editor defines the speed of the vehicle object, then defines the tracking to find out the vehicle speed in the video target, and finally removes the tracking because it is not in the tracking region that has been previously determined via the cascade file. Finally, the test video includes lines of code that can be used to download the model analysis results.

After defining the speed, tracking, and deletion. The program will run, then download the output.avi file in which the output video contains the results of the analysis from the program that was run before.

# 3. Model Realization and Visualization
Model Realization and Visualization will focus on how each model is built, how each photo or video from various datasets is used, and the output of each machine learning model is presented both in the form of photos and in the form of videos.

# 3.1 Realization and Visualization of Vehicle Type Detection Model
A. Build machine learning models
This section will provide an explanation of the code required to develop the model to perform the tasks it desires.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-6-page-00001.jpg width="500" height="500">
</p>

To insert files into Google Collaboratory, the code above is used to import files from Google Drive.


<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-7-page-00001.jpg width="500" height="500">
</p>

The code above is used to point to the Google Collab directory to fetch the data, unzip it, and then point to the Google directory to train the custom model in the selected directory. 

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-8-page-00001.jpg width="500" height="500">
</p>

With this code, you can edit the images in the dataset and insert the images into specific classes.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-10-page-00001.jpg width="500" height="500">
</p>

The model shows that the convolutional neural network (cnn) architecture is used. model.compile is used for metrics, optimizer, and setup loss. History is the model. Features are used to instruct the model

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-11-page-00001.jpg width="500" height="500">
</p>

To include yolov5 in the model you have to get the code to call it from the github directory.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-12-page-00001.jpg width="500" height="300">
</p>

Use this package to download the libraries needed by Yolov5

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-13-page-00001.jpg width="500" height="300">
</p>

This code is used to feed the video input to Google Collaboratory for analysis by the model.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-14-page-00001.jpg width="500" height="300">
</p>

Calls the detect.py file to identify objects in the video

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-15-page-00001.jpg width="500" height="300">
</p>

Currently, analysis results can be downloaded to see how well the model can analyze the videos that have been inserted.

B. Processing datasets to become data results
This section, so that the model can work with the desired dataset, will explain the origin of the dataset used to learn to understand it.

The dataset used is a collection of images in .jpg format. This dataset can be accessed for free via Kaggle, which also functions as a provider of images and videos in various formats.

The dataset that you have obtained is stored on Google Drive in a folder called dataset.zip.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-16-page-00001.jpg width="500" height="300">
</p>

To allow datasets to be downloaded automatically, an authentication process is performed on Google Collab before gaining access to Google Drive. change the settings where datasets are stored and set the directory where the dataset files are located, as shown below:

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-17-page-00001.jpg width="500" height="300">
</p>

After the dataset is entered properly, the model will process the dataset to analyze it and provide analysis results. 

C. Model for output in machine learning
This section The results of the machine learning model will be shown in the picture. The output of this model is video, which is presented in this report as images.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-18-page-00001.jpg width="500" height="500">
</p>

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-19-page-00001.jpg width="500" height="300">
</p>

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-20-page-00001.jpg width="500" height="300">
</p>

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-21-page-00001.jpg width="500" height="300">
</p>

The collection of pictures above is footage from the model.

# 3.2 Realisasi dan Visualisasi Model deteksi Helm Pengendara
A. Build machine learning models
In this section. It describes the code that must exist for model development so that the model can perform the desired task.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-22-page-00001.jpg width="500" height="300">
</p>

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-23-page-00001.jpg width="500" height="300">
</p>

The above code works to ensure that the running runtime uses the GPU and then calls yolov5 as a library to detect the object.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-24-page-00001.jpg width="500" height="300">
</p>

To download some of the libraries required by the model, dependency installation is used.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-25-page-00001.jpg width="500" height="300">
</p>
The code above is used to call the dataset from roboflow, which is used by roboflow to store the dataset for the model to train.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-26-page-00001.jpg width="500" height="900">
</p>

If yolov5 is implemented in code, the architectural form is as follows.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-27-page-00001.jpg width="500" height="500">
</p>

This code is used to train a model in google collaboratory

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-28-page-00001.jpg width="500" height="300">
</p>
Here, trained weights that have been trained from previous training are used to retrain to improve model accuracy.

B. Processing datasets to become data results
In this section, we provide an explanation of the data sources used to learn to understand the machine learning model, so that the model can function in the desired way.

The dataset used is a collection of images in .jpg format. This dataset can be accessed for free from Roboflow, which also functions as a provider of photo and video recordings in various formats.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-29-page-00001.jpg width="500" height="300">
</p>

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-30-page-00001.jpg width="700" height="300">
</p>

The image above shows the Annotated process in Roboflow. In addition to the image of two people wearing helmets, you can see a green to yellow brass box labeled as a helmet. Other than the purple box labeled as no helmet, a woman is not seen in figure 3.31.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-31-page-00001.jpg width="500" height="300">
</p>

The box coordinates discussed earlier are shown in the file above. The number one in the figure indicates the label class, while the decimal number indicates the box position discussed earlier.

Roboflow creates annotated images so that the created model can read them. To mark up an image, roboflow places a grid on the image so that the machine learning model can identify the exact object and coordinates of the box. The roboflow system will input the box coordination into the format desired by the user. file storage, in this case file.txt

After the required dataset has been processed through an annotated image process. The dataset will be inserted into the created folder so that the set can be divided into three parts

Training Set 69%
Validation Set 19%
Testing Set 11%

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-32-page-00001.jpg width="500" height="300">
</p>
For this example, the dataset split is split 25:7:4 to prevent overfitting when training the machine learning model.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-33-page-00001.jpg width="500" height="300">
</p>

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-34-page-00001.jpg width="500" height="300">
</p>

Development process and data preprocessing. Roboflow is given the freedom in these two stages to choose the method for each process in the data augmentation and preprocessing sections. In this case, the settings only manage those two processes, as shown in the image above.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-35-page-00001.jpg width="500" height="600">
</p>

Before images can be used as datasets in Google Collab, this is the final stage. At this time, Roboflow offers a variety of version size options to work with.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-36-page-00001.jpg width="500" height="300">
</p>

Once the image is complete, arrange it. The image creation process has been completed, which will be used for collaboration in Google Collab. Export the dataset file in code form to enable calling it into Google Collab.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-37-page-00001.jpg width="500" height="300">
</p>

The following is the result of exporting the code in Google Collab.

C. Model for output in machine learning
In this section. The results of the machine learning model will be shown in the form of photo footage.

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-38-page-00001.jpg width="500" height="300">
</p>

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-39-page-00001.jpg width="500" height="300">
</p>

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-40-page-00001.jpg width="500" height="300">
</p>

<p align = "center">
  <img src = https://github.com/MausDennis/Driver-Violation-in-Jakarta-Polytechnic-State/blob/main/Footage%20photo/Kumpulan%20Photo%20untuk%20porto%20ml%20(1)-41-page-00001.jpg width="500" height="300">
</p>

The collection of pictures above is footage from the model.

# 3.3 Realisasi dan Visualisasi Model deteksi Plat Nomor Kendaraan
A. Build machine learning models
This section will provide an explanation of the code required to develop the model to perform the tasks it desires.

====> Gambar 3. 43 Memanggil Imutils <====

To manipulate images, the Imutils library supports models by performing translation, rotation, scaling, and skeletonization.

====> Gambar 3. 44 Memanggil Gambar untuk diubah seutuhnya menjadi warna abu - abu <====

The code enters the image for processing. Images are converted to ash before processing.

====> Gambar 3. 45 Gambar di filter dan dicari tepinya <====

An image that has been grayed out is shown in the image above. At this point, the image is filtered with noise reduction and edge recognition to produce a contoured image with a predominance of black.

====> Gambar 3. 46 Kode untuk mengetahui dugaan plat nomor berada <====

The code above is used to identify the suspected location of the license plate.
	
====> Gambar 3. 47 Kode untuk memanggil kontur dan masking <====

The contour is called and the masking process starts with the code above.

====> Gambar 3. 48 Kode untuk melakukan masking dengan tujuan mencari lempengan plat nomor lalu gambar dikerat <====

The above code is used to close by looking for the number plate plate and then drawing it.

====> Gambar 3. 49 Kode agar model dapat membaca tulisan atau angka yang terdapat di lempengan plat nomor <====

The model uses the code above to read the writing or numbers on the license plate.

====> Gambar 3. 50 Kode untuk menampilkan hasil bacaan berbarengan dengan foto inputan untuk dideteksi plat nomornya <====

Reading results are displayed with the code above along with picture input to detect license plates.

B. Processing datasets to become data results
This section, so that the model can work with the desired dataset, will explain the origin of the dataset used to learn to understand it.

The license plate dataset is taken from Kaggle, then entered into the Kaggle code editor. This is done by inserting the dataset into the far right of the browser view.

====> Gambar 3. 51 Proses mencari dataset di kaggle <====

The image above shows the display of the dataset search process using Kaggle.

====> Gambar 3. 52 Direktori model plat nomor di kaggle <====

The dataset is ready to use in the Kaggle code editor

C. Model for output in machine learning

This section The results of the machine learning model will be shown in the picture.

====> Gambar 3. 53 Mobil (1) <====

====> Gambar 3. 54 Mobil (2) <====

====> Gambar 3. 55 Mobil (3) <====

====> Gambar 3. 56 Plat Nomor (1) <====

====> Gambar 3. 57 Plat Nomor (2) <====

====> Gambar 3. 58 Mobil (4) <====

Most of the images above are from the model.

# 3.4 Realization and Visualization of the Vehicle Speed Detection Model
A. Build machine learning models
This section will provide an explanation of the code required to develop the model to perform the tasks it desires.

====> Gambar 3. 59 Kode untuk menginstall opencv di kaggle <====

Opencv is used to detect objects in an image or video

====> Gambar 3. 60 Menginstall ubuntu package <====

Ubuntu package installation to help the model determine the speed.

====> Gambar 3. 61 Algoritma Kecepatan <====

This image shows the speed algorithm used to identify the speed of a motorized vehicle.

B. Processing datasets to become data results
This section, so that the model can work with the desired dataset, will explain the origin of the dataset used to learn to understand it.

When you find a dataset, you can find a license plate and then enter the dataset into the Kaggle code editor instantly. This allows you to use it as a material for machine learning models.

====> Gambar 3. 62 Proses mencari dataset di kaggle <====

To select a dataset, you will see a pop-up image. If you've downloaded the previous dataset to Kaggle, you can use it here as well.

====> Gambar 3. 63 Direktori model kecepatan kendaraan di kaggle <==== 

This image shows that the dataset was successfully entered into the input on kaggle

C. Model for output in machine learning
This section The results of the machine learning model will be shown in the picture. The output of this model is video, which is presented in this report as images.

====> Gambar 3. 64 Model Kecepatan <====

====> Gambar 3. 65 Model Kecepatan di PNJ <====

Most of the images above are from the model.
