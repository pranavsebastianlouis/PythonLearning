```python
import os
from os import path
import datetime
from datetime import date,time,timedelta
import time
```

## OS name


```python
print(os.name)
```

    nt
    

## Check if path exists


```python
path.exists("sample.txt")
```




    True



## Check if the item is a file or a directory.


```python
path.isfile("sample.txt")
```




    True




```python
path.isdir("sample.txt")
```




    False



## Find the complete path of the item


```python
c = path.realpath("sample.txt")
print(c)
```

    E:\ICT\sample.txt
    

## Split the path into a tuple containing the path and filename seperate.


```python
path.split(c)
```




    ('E:\\ICT', 'sample.txt')



## Get the modification time of the file.


```python
mod_time = path.getmtime("sample.txt")
mod_time# this will be in seconds since the last epoch that is Jan 1 1970
```




    1740637955.0584495



## To get the modification time in human readable format use  
### Method _ 1


```python
time.ctime(mod_time)
```




    'Thu Feb 27 12:02:35 2025'



### Method_2


```python
print(datetime.datetime.fromtimestamp(mod_time)) #use print()
```

    2025-02-27 12:02:35.058450
    

## To get how much time has elapsed since last modification.


```python
print(datetime.datetime.now()- datetime.datetime.fromtimestamp(mod_time))# now() gives the current time.
```

    2 days, 11:34:27.383430
    


```python
td = datetime.datetime.now()- datetime.datetime.fromtimestamp(mod_time) #we are creating a time delta
```


```python
#we can use object td to showus in seconds or minutes as required
print(td.total_seconds())
```

    3582.2915861
    


```python
def total_minutes(time_delta):
    return f"{(time_delta.total_seconds()/60)} minutes."
total_minutes(td)
```




    '3582.2915861 minutes.'



## Get the creation time of file


```python
path.getctime('sample.txt')
```




    1740636765.6858072



## To get it in human readable format we can either use time.ctime() or datetime.fromtimestamp()


```python
time.ctime(path.getctime('sample.txt'))
```




    'Thu Feb 27 11:42:45 2025'




```python
#or
print(datetime.datetime.fromtimestamp(path.getctime("sample.txt")))
```

    2025-02-27 11:42:45.685807
    


```python
creation_t = (datetime.datetime.fromtimestamp(path.getctime("sample.txt"))) 
```

## How much time has elapsed since creation ; we need to create a time delta


```python
td_creation = datetime.datetime.now() - creation_t
print(td_creation)
```

    2 days, 12:10:35.657104
    


```python
print(td_creation.total_seconds())# to see how much seconds since created
```

    216635.657104
    


```python
total_minutes(td_creation) # a function created earlier to show minutes
```




    '3610.594285066667 minutes.'




```python

```


```python

```
