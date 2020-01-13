
# Automated documentation using pdoc

![https://pandalearnstocode.in/slide/pdoc_funny.jpg](https://pandalearnstocode.in/slide/pdoc_funny.jpg)

## List of dependency

```python
aiofiles==0.4.0
pdoc3==0.7.2
fastapi==0.46.0
```

  

## Installing depedency

```shell
conda create --name documentation --file requirements.txt
conda activate documentation
conda deactivate
```

  

## Project structure

  
![https://pandalearnstocode.in/slide/doc_dir_str.jpg](https://pandalearnstocode.in/slide/doc_dir_str.jpg)  

## Python file

```python
def  addition(first_number: int, second_number: float) -> float:
"""This function will perform addition of two numbers.
Parameters
----------
first_number : int
	the 1st arg has to be an int
second_number : float
	the 2nd arg has to be an float
Returns
-------
float
	the result of sum of an int and a float will be a float
"""
result: float  = first_number + second_number
return result
```  

## Install autodoc extension in VSC

Go to setting and select default docstring generation style to be numpy. But it is not exactly numpy. The thrid bracket has to be removed from the args and returns defintion like above and it will work as expected.


## Generate documentation

```shell
# In development
pdoc --html documentation
# In staging or production
pdoc --html --config show_source_code=False documentation
```

## Serve HTML site using fastapi


### Content of doc_app.py

```python
from fastapi import FastAPI
from starlette.staticfiles import StaticFiles
app = FastAPI()
app.mount("/documentation", StaticFiles(directory="documentation"))
```

  

### Start and access doc app server

```shell
cd html && uvicorn doc_app:app --reload
open -a "Google Chrome" http://127.0.0.1:8000/documentation/index.html
```

## Extract dependency

```shell
pip3 freeze > requirements.txt
```

## Deactivate envs

```shell
conda deactivate
```

## Further steps

Create a shell script which will be executated in the time of deployment or create a pre-commit hook which will create the documentation side ready before sending to git and when it will be deployed respective folder will be picked from the respective directory and displayed.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYwNTkzMjQ1LC0yMDQ3ODQ0MDg5LDY1Mz
YzNTY1MywtMTYwMDg1OTI2MywtMTQxMTQ0NzEzMV19
-->