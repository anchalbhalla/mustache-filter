# mustache-filter 

Create a mustache filter similar to a Snapchat filter by following these steps: 


## Pre requisites 

* Install python version 3.x  
https://www.python.org/downloads/

* Intall opencv  
```
pip install opencv-python
```
* Install numpy 
```
python3 -m pip install numpy
```


## Steps 

1. Create an IBM Cloud account 

2. Create a Functions service from the catalog
* ![alt text](https://github.com/anchalbhalla/mustache-filter/blob/master/images/function.png)
 
    * Create an Action  
    ![alt text](https://github.com/anchalbhalla/mustache-filter/blob/master/images/create-func.png) 
    

3. Copy paste this python code to the Code section of the service:   
   
   * Save the code 
   
   * Enable Web Action under Endpoints and copy the HTTPS URL
   ![alt text](https://github.com/anchalbhalla/mustache-filter/blob/master/images/web.png) 
   
   
``` 

import sys 
import random

def main(dict):
  
  mus_urls = ['https://sublimerobots.com/wp-content/uploads/2014/12/mustache.png', 'https://i.pinimg.com/originals/67/2e/0f/672e0f6f71ebe08a5029a89e85df1e18.png', 'https://images.vexels.com/media/users/3/130978/isolated/lists/f932a333154f1d6bff554c1010466f00-hipster-mustache-5.png', 'https://www.papilbo.com/2743-large_default/basic-classi-con-fiocco-blu.jpg', 'https://www.660citynews.com/wp-content/blogs.dir/sites/8/2016/11/01/moustache.png' ]

  index = random.randint(0, len(mus_urls)-1)
  print(mus_urls[index])  
 
  return {'url':mus_urls[index]}
  
```
   
4. Download the serverless-detection.py and the haar cascade files (reference: https://github.com/opencv/opencv/tree/master/data/haarcascades)

5. Edit the file: 
   
   * Add your HTTPS URL (not the REST API link) from the Cloud Functions service

6. Run the following command on the terminal to execute the application: 
``` 
python serverless-detection.py 
```


## The Architecture 
![alt text](https://github.com/anchalbhalla/mustache-filter/blob/master/images/architecture.jpg)


## The Process 
![alt text](https://github.com/anchalbhalla/mustache-filter/blob/master/images/process-Diagram.png)
