

Application:

The assignment is on developing RESTful Web Services. I have used flask framework with Python to create a REST API to host weather information.  
The data used is weather information of Cincinnati for the last 3 years. The attributes are  
DATE in YYYYMMDD format,  
TMAX - Maximum Temperature for the particular date,  
TMIN - Minimum Temperature for the particular date.  
 
I have used in memory to retrieve the data according to the various endpoints in the URL. 
Forecast Model used in this is averaging the corresponding temperatures of all the years in the database for a particular date.  

**GET:**  
http://18.217.178.247/historical/ - Retrieves the list of all the dates that are available in the database in a JSON Array.  
http://18.217.178.247/historical/<dateYYYYMMDD> - Retrieves the Max and Min temperature for the date passed, if not available throws 404 error.  
  
**Ex:** http://18.217.178.247/historical/20130101  
**Output:** {"DATE": "20130101", "TMAX": 34, "TMIN": 26}  
  
**Ex:** http://18.217.178.247/historical/20190101  
**Output:** 404 - Not Found  
  
http://18.217.178.247/forecast/<dateYYYYMMDD> - Retrieves the Max and Min temperature for the date passed along with the next 7 days.  
**Ex:** http://18.217.178.247/forecast/20200822  
**Output:**  
[  
  {  
    "DATE": "20200822",   
    "TMAX": 83.42,   
    "TMIN": 61.68  
  },   
  {  
    "DATE": "20200823",   
    "TMAX": 86.96,   
    "TMIN": 62.9  
  },   
  {  
    "DATE": "20200824",   
    "TMAX": 85.9,   
    "TMIN": 62.84  
  },   
  {  
    "DATE": "20200825",   
    "TMAX": 87.64,   
    "TMIN": 65.84  
  },   
  {  
    "DATE": "20200826",   
    "TMAX": 88.46,   
    "TMIN": 65.9  
  },   
  {  
    "DATE": "20200827",   
    "TMAX": 89.1,   
    "TMIN": 67.94  
  },   
  {  
    "DATE": "20200828",   
    "TMAX": 90.32,   
    "TMIN": 67.74  
  }  
]  
  
**POST:**  
http://18.217.178.247/historical/ - To add weather information for a particular day  
Posts the temperature information with HTTP 201 Response by appending the entered information into existing JSON Array.  
  
**DELETE:**  
http://18.217.178.247/historical/<dateYYYYMMDD> - Delete method to delete the temperature information for a particular day  
  
**Used Technologies:** Python 2.7, Flask, JSON  
  
The application has been hosted on:  
**Base URL :** http://18.217.178.247  
  
The entire functionality has been done by defining various methods for each purpose.   
Source: ``"__init__.py"`` 

**References:**   
https://dzone.com/articles/restful-web-services-with-python-flask  
https://www.codementor.io/sagaragarwal94/building-a-basic-restful-api-in-python-58k02xsiq  
https://blog.miguelgrinberg.com/post/designing-a-restful-api-with-python-and-flask  
  
------------------------------------------------------------------------------------------   
  
**Application :** http://18.217.178.247  
**Github      :** https://github.uc.edu/gondinm/Cloud_Computing/tree/master/HW2  
**Readme:** https://github.uc.edu/gondinm/Cloud_Computing/blob/master/HW2/REST.md  
  
------------------------------------------------------------------------------------------  
