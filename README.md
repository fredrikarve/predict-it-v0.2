# Predict-IT project v0.2
Delivered 2017-11-02.
***  


### **Installation**   
:snake: Updated 2017-11-02.
1.  The program is best run on PyCharm. We have been using a Virtual Environment with Python 3.6 or Anaconda environment (also Python 3.6).  
2. Anaconda  
  a)  You may have to install Anaconda (latest version) to retrieve all the packages. For MacOS it was not required.   
  b) Anaconda installation guide for Windows    
    1. [Download](https://www.anaconda.com/download/) Anaconda installer version 5.0.0.  
    2. Install Anaconda by following the instructions.  
    3. When Anaconda has been successfully installed, go into PyCharm and chose anaconda environment as the interpreter for your project.  
    4. Open Anaconda prompt which was installed with anaconda.  
    5. Iterate to the path of your project.  
    6. Type `conda install tensorflow` and wait for the installation to finish.  
    7. Type `conda update html5lib` and accept all updates or downgrades.  
    8. Now you can install all libraries that need to be installed with pip by typing `pip install PACKAGENAME`  
    9. If you type `conda list` you will see a list of all installed packages.  
3. Install requirements in requirements.txt in root directory  
4. Goto /data/news and run in this order:
 - `setup_news_database.py` Creates a database to store the news. 
 - `news_categorization_model.py` Downloads and trains the categorization model.
 - `run_import_articles.py` Collects news articles. (5 articles are required before you can access the flask-app)
5. Goto /machine_learning/flask_REST_API and run `api.py`. The ML-model will train once you run the API. You can find info about the training as output from `api.py`.
6. Run `run.py` in /flask  
7. Go to  http://127.0.0.1:5000/ to see the Flask application  
8. Login using "admin" as username and password.  
  a) You will see the operators views when logging in.
  b) When pressing the user demo The ML-model will load and eventually return a prediction. This indicates if the user would likely enjoy the movie or not. The prediction might vary from 1-5 where 5 is good suggestion and 1 is a bad suggestion. Might take a few seconds.  
  c) Right now the model only is trained two times (`EPOCH_MAX = 2` in `/machine_learning/prediction/svd_train_val.py`). This can be changed to get better accuracy. After the model is complete you can find information about each run in the console.  

***

### **Structure**
Updated on 2017-11-02.  
This is the ~~first~~ second version of the structure. The idea is to seperate the project into three main parts: data, ML and GUI. You will find a few _.gitkeep_-files in a few directories. GitLab does not allow you to create empty-directories so as soon as there are more files they can be removed.    
- **/data**                
  - /content         
  - /news       
  - /user_data       
- **/machine learning**   
  - /prediction   
  - /matching        
  - /libraries  
  - /flask_REST_API  
- **/flask**
  - /app
  - /db_repository
***