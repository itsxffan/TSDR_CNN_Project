# Traffic Sign Classification Project (SA)
 
# Step 1 - Executables:
## Method 1:
All the associated files with the project can be found from the drop-box:
(Saffan Ahmed – City University One Drive) [https://www.dropbox.com/sh/4g5edoiz3hdopjz/AABJptU8Q51fo1i5ZkPaofa9a?dl=0] 

## Method 2:
Alternatively from ‘Saffan Ahmed’ GitHub (Repository publicly available for cloning):
https://github.com/itsxffan/TSDR_CNN_Project

Note: If GitHub repository is cloned it’s important to carry out the following steps to create missing folders. 

Open up the file path to where you stored the repository in terminal:
-	mkdir data
-	mkdir Checkpoint
-	mkdir GTRSB


/Checkpoint <- This folder or path (Set empty) will contain the saved model sessions, once each model architecture is trained the model architecture and specified parameters will be stored here as an index or checkpoint, which later on can be used to produce chart analysis.

/data <- This folder or path (Set empty) will contain all the training and testing dataset used to train each model. 

/GTRSB <- This folder or path (Set empty) will contain generic readme txt files for images (not important). 

/images <- This folder or path will contain sample images from the web used to evaluate the model.

/Model_Results <- This folder or path will contain all result images that author had derived from training.

/pipeline <- This folder or path will contain 3 python files (network, session, pipeline)

Traffic_Sign_Classification_LeNet_v1_ipynb <- This notebook file is main file constructed by author contains all data analysis, image pre-processing and evaluation.

TrafficSignNames.csv <- File listing different traffic-sign names associated with their class ID.
![image](https://user-images.githubusercontent.com/20278752/116826426-d5297580-ab8b-11eb-8c07-2b9078523640.png)

Step 2 – Environment Setup:
Note: Due to hardware limitation the author was not run model training on local machine due to not having a powerful GPU. Training CNN models are computationally expensive hence why the author relied upon ‘Gradiant Paperspace’ machine learning platform. They offered a cloud hosted GPU machine. This machine provided all the prerequisite libraries for machine learning, those libraries that were missing the author manually installed those libraries through Jupyter environment terminal using ‘pip’ command. 

Method 1:

As a result anaconda environment had not been used given hardware limitation however instructions below have been defined to allow testers to utilise anaconda if needed.
For those who would like to run the Jupyter notebook on their local machine please use the following: 

Anaconda Setup:
Setup required python libraries as follows:
conda env create -f environments-gpu.yml  # with GPU

If you have no CUDA-enabled GPU, you can use the following:
conda env create -f environments.yml  # with CPU

Notebook can be started as follows:
jupyter notebook Traffic_Sign_Classification_LeNet_v1_ipynb

Method 2:

Gradiant Paperspace Notebook (TSDR_CNN_Project):
https://console.paperspace.com/saffan-a-private-workspace/notebook/rgkpcibe3wkhu76

For those who don’t have a powerful GPU ‘Gradient Paperspace’ ML platform could be used. Follow link above to launch notebook, you will need to create an account to run .

 

 

Select Machine Instance:
This is where you can select a GPU to use the author utilised the free-instance (Free GPU option) this is a machine that has an 8-core CPU (Quadro M4000 processor) with GPU support and 30 GB RAM. Time limit for free-GPU’s is up to 6 hours long. So after 6 hours the machine will shut down and notebook will stop working hence why author had to always restart machine every 6 hours limiting the tests that could be carried out for author.

 

Once machine chosen then start machine instance (this will take 30 sec to 1 min to get machine to run). Then proceed to setup libraries that are missing:

Open jupyter notebook terminal on ML platform then installs all pre-requisite library packages:

 

pip installs:
-	pip install numpy
-	pip install matplotlib
-	pip install pillow
-	pip install opencv-python-headless<4.3
-	pip install scikit-learn
-	pip install scipy
-	pip install pandas
-	pip install scikit-learn

Step 3 – Downloading Dataset (How-To):
Dataset used is from public-domain – this domain is from a research institute whom have a collection of the largest dataset available for traffic-sign images.
https://sid.erda.dk/public/archives/daaeac0d7ce1152aea9b61d9f1e19370/published-archive.html 

# use wget or curl (enter commands into Terminal (Jupyter Environment)
- wget https://sid.erda.dk/public/archives/daaeac0d7ce1152aea9b61d9f1e19370/GTSRB_Final_Training_Images.zip
- unzip GTSRB_Final_Training_Images.zip
- mv GTSRB/Final_Training data/

- wget https://sid.erda.dk/public/archives/daaeac0d7ce1152aea9b61d9f1e19370/GTSRB_Final_Test_Images.zip
- unzip GTSRB_Final_Test_Images.zip
- mv GTSRB/Final_Test/ data/

- wget https://sid.erda.dk/public/archives/daaeac0d7ce1152aea9b61d9f1e19370/GTSRB_Final_Test_GT.zip
- unzip GTSRB_Final_Test_GT.zip
- mv GT-final_test.csv data/Final_Test/Images/













## Folder Structure

The training images are organized in folders by category.  Each folder is meant for one category (i.e. stop sign) and has a label file (.csv) which is actually semi-colon delimited (not comma delimited).

```
data
 + Final_Training
    + Images
        + 00000
            + 00000_00000.ppm
            + 00000_00001.ppm
            ...    
            + GT-00000.csv
        + 00001
            + 00000_00000.ppm
            + 00000_00001.ppm
            ...    
            + GT-00001.csv
        ...
```

All images are stored in the PPM format ([Portable Pixmap, P6](http://en.wikipedia.org/wiki/Netpbm_format)).  You'll need to install both `matplotlib` and `pillow` to handle such image format.  If you use one of the evironments yml files in this repository, this will be taken care of.

Test images do not have category folders but all are kept in one place with one label file.

```
data
 + Final_Test
    + Images
        + 00000.ppm
        + 00001.ppm
        + ...
        + GT-final_test.csv      # Extended annotations including class ids
        + GT-final_test.test.csv
```
 

Pipeline Framework:
All of the Python classes and methods for building pipelines use TensorFlow and Scikit-Pipeline Learn's system which can be found in the pipeline folder. To test various pre-processing and network architecture scenarios, I used pipelines extensively.

After that, a network is transformed into an estimator that can be used with Scikit-Pipeline Learn's object. I also have a helper class that can be used to convert any functions into a transformer that can be used in a Pipeline object.

Step 4 – Final Disclaimer:
Once all above steps have been completed you can simply open up the ‘Traffic_Sign_Classification_LeNet_v1.ipynb’ file and run the code segments top to bottom in order.
Despite using a cloud hosted GPU model, training models are again computationally expensive they can often take 30 min to 6 hrs + each to run of course dependent on how complex the model becomes (more parameters, more epochs) all require more time. 

![image](https://user-images.githubusercontent.com/20278752/116826474-17eb4d80-ab8c-11eb-81c8-53f570301a17.png)

