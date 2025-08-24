### Salt and Sediment Formation Classification
---
### Introduction
---
Several areas of Earth with large accumulations of oil and gas also have huge deposits of salt below the surface.
<br>
But unfortunately, knowing where large salt deposits are precisely is very difficult. Professional seismic imaging still requires expert human interpretation of salt bodies. This leads to very subjective, highly variable renderings.
<br />

In this project, I aim to build an algorithm that segments regions that contain salt. The Convolutional Neural Network (CNN) Model which will be used is `U-Net`.
Note: I would say a passing understanding of Exploration Geophysic

### Data
---
Note: Data is taken from [kaggle](https://www.kaggle.com/competitions/tgs-salt-identification-challenge/data).
The data comes in the form of seismic images, where some show normal seismic with possible O&G reservoirs or seismic which contains salt deposits.
The actual data itself was provided by [TGS | Energy Data & Intelligence](https://www.tgs.com/).
The dataset can also be downloaded by using the `kaggle API`.

* `$ pip install kaggle`
* `$ kaggle competitions download -c tgs-salt-identification-challenge`


<br>
The data is a set of images chosen at various locations chosen at random in the subsurface. The images are 101 x 101 pixels and each pixel is classified as either salt or sediment. In addition to the seismic images, the depth of the imaged location is provided for each image.
<br />


#### Basic Overview of Seismic Data Exploration ####
---
Seismic data is collected using seismic reflection. The method requires a controlled seismic source of energy, such as compressed air or a seismic vibrator, and sensors record the reflection from rock interfaces within the subsurface. The recorded data is then processed to create a 3D view of earth’s interior. Reflection seismology is similar to X-ray, sonar and echolocation.

A seismic image is produced from imaging the reflection coming from rock boundaries. The seismic image shows the boundaries between different rock types. In theory, the strength of reflection is directly proportional to the difference in the physical properties on either sides of the interface. While seismic images show rock boundaries, they don't say much about the rock themselves; some rocks are easy to identify while some are difficult.

There are several areas of the world where there are vast quantities of salt in the subsurface. One of the challenges of seismic imaging is to identify the part of subsurface which is salt. Salt has characteristics that makes it both simple and hard to identify. Salt density is usually 2.14 g/cc which is lower than most surrounding rocks. The seismic velocity of salt is 4.5 km/sec, which is usually faster than its surrounding rocks. This difference creates a sharp reflection at the salt-sediment interface. Usually salt is an amorphous rock without much internal structure. This means that there is typically not much reflectivity inside the salt, unless there are sediments trapped inside it. The unusually high seismic velocity of salt can create problems with seismic imaging.


### Requirements
---
* `Python 3.x`
* `Pandas`
* `NumPy`
* `Matplotlib`
* `TensorFlow`
* `Keras`
* `tqdm`; used for status bars during model-building; tells us whats going on. E.g. is the precision of the model improving with increasing epochs..?
* `scikit-image`
* `scikit-learn`
* `NIVIDIA GPU`. This isn't a requirement but the application is computationally demanding and building the model may take some time. 
* I would say a passing understanding in Exploration Geophysics/Geology would be very helpful so you can really see how helpful Deep Learning is in the O & G Industry.


### Computational Struggles.
---
As mentioned, this project is computationally demanding on the CPU, given that the number of epochs used is 25.
However, you can get some free GPUs which will help speed this project up! Visit Google's [Colab](https://colab.research.google.com/).



### Instructions for Project Use
---
* `$ git clone https://github.com/MRLintern/Salt_and_Sediment_Classification.git`
* Go to [kaggle](https://www.kaggle.com/competitions/tgs-salt-identification-challenge/data) and download the dataset.
* Unzip the dataset to the `Salt_and_Sediment_Classification` directory if you choose not to use the `Kaggle API`.
* Once you have the dataset, execute each cell. Alternatively, copy and paste the code into your own notebook.

### Whats Next?
---
Might look into using a different CNN and measuring its performance against U-Net by looking at their respective **learning curves**.
