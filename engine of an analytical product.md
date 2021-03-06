# A mental model for buliding engine of an analytical product

Curretly, I am working for The Nielsen Company in Product Development team. As a part of this role in past three years I have developed an mental model building engine of an analytical product. There is a huge amount of subjectivity involved here, but this thing works quite well for me. It may or may not be useful for everyone. In sub subsequent posts I will try to break down required part of this process but this post will be mostly an overview regarding the mental model of the analytical side of the product development. 

## The end to end workflow


![](https://pandalearnstocode.in/mental_model/a_mental_model_of_analytical_product_engine.png)

## Workflow in details

### Buisness problem

A business problem is a series of statement which has to be converted into an analytical solution at a later stage. For example, for a given efficiency level of multiple resources, how is it possible to achieve maximum efficiency for a given budget. Lets take hiring as an example. Suppose, there are 100 cadidates are present in a pool of shortlisted candidates. But if can only hire for 10 positions. For each different level of position there is a upper and lower bound of salary and altogher there is a total amount of budget you can allocate to hire these 10 floks. Now, what which candidates you should select in order maximise the productivity for the given budget.

### Analytical problem statement and input, output schema

From high level view this does not look like an analytical problem. But lets take a leap of faith and consider that it can be boiled down to an LPP problem. Now, converting this series of statements to a minimization problem for given bound constraint and equality constraint is the first thing which has to be done. After formulating the problem, one has to finialise that which informations are required to solve the analytical problem and which information has to be shown back to the user. After making a list of input and output, a JSON schema has to be desinged. This is important to capture all the requirment at this point because this JSON schema is the contract between the backend and engine of the application. Also, there are some of the things must be taken into consideration when designing the schema:
* Data should not be repetative.
* Minimal sufficicient data should be sent in a network call.
* Datatype of keys must be fixed.
* Set of validation rules must be derived which will be later converted to validation. 
* Request and response JSON schema has to be 100% specified in this stage.

There are some other points but they can be ignore and touched upon when we will revisit this topic.

### Developing a static code

The formulated math problem has to be converted into a code in this section. This code will take a input from an existing dataset and will produce result. While developing this code one must remember that this code will be converted late to an interactive app. So, this is important to make all the inputs dynamic and perform things in a small functions. These function should do less thing but should do that in an robust manner. 

### Communicate inital set of result for the data

After developing the static code take a dump of the result. Present them a format which is acceptable to all the stakeholder. If the result and methodology looks promising then proceed to the next step. Otherwise go back to formulation of analytical problem and IO schema stage and reiterate.

#### Tools:

* Presentation (ios slide, beamer slide, RISE slide, xaringan and others)
* Technical document (pdf document using markdown, pandoc and LaTeX)
* Notebooks (nteract, Jupyter or Rmarkdown notebooks)

### Interactive proof of concept app

Convert this static code to a proof of concept app by introducing dynamic input. By changing the input one will be able to check the algorithm with multiple data source and user input. The UI should be minimal, functional and should capture all the required input and produce desired output.

#### Tools:

*  R (shiny)
* Python (jupyter + ipython widget, voila, panel, bokeh and others)
* Interactive plotting (plotly, html widget)
* Plotting (seaborn, pyviz, matplotlib, ggplot2)
* Desktop application (Electron.js)
* Basic testing in notebook using papermill

### UAT of proof of concept app

Share the interative application with the concerned stakeholders, so that they can play with the application. If all the stakeholders feel that this algorithm solves the business problem in an efficient manner then proceed to the next step or depedening on the type of problem go back to any of the previous step. Suppose, if there is a concern related to the speed of the application go back to static code stage and make modification if possible. If there is some result inconsistency related issue then go back to the problem formulation stage and may be try out some other algorithm. This call is a subjective call depedening upon the hurdle.

### Production code development

After finalizing the methodology, data, user input and required output the code has to be converted to a production quality code. The objective of this stage is to produce a code which is well documented, readable and well optimized. 

#### Tools:

* Use minimum and stable libraries
* Document code with comment and docstring (sphix)
* There should a validation arugments in this section (mypy)
* Error handelling (base python)
* Structured logs (structured logs, coloredlogs, eliot tree, tidylog)
* Reproducible eviourment (pip, conda)
* Code profiling (cprofiler, lineprofiler, snakeviz, jupyer time magic, profileviz and others)
* Exploration and implimentation of data schema (dplyr, tidyr, pandas and pandas-profiling)
* Basic ETL (pandas, janitor)
* Advanced computation (Numpy, Numba, Purrr, Tidyverse)
* Scientific computing (Scipy, Scikit-learn, statmodels, stats, MASS, caret and many more)
* Scale up and Scale out (purrrlyr, dask, modin, vaex)

### Testing

Standard testing will not always very useful for data science projects but it is not possible to discard standard testing module as well. A combination of following testing can be very useful for data science projects,

#### Tools:

* Unit test (pytest)
* Property based testing (Hypothesis)
* Testing with Simulated data (Faker)
* Design by contract (contract)
* Other libraries for Data Science (testthat etc)


### QA and QC

In order to make code base more readable this is important to maintain code quality in time. It helps in refacoring and maintaing the code. Speically in case of data science project various transformation, imputation, grouping and preprocessing is done. So, this is important to capture all the minute details as part of docstring, comment, logs and others. Also, in oder to match the same naming convension, reability index and styling this is import to make sure the following checks has been performed before the code is commited to the code base.

* Static typing (mypy)
* Doc string (sphinx, doc8, pydocstyle)
* Linting (flake8,pylint, pyflakes, Lintr)
* Maintainablity Index (Wily, Maccabe)
* Code styling (pycodestyle, autopep, pep8-naming)
* Code coverage
* Comment highlighting


### Building a package or library
After the production code passes the code quality it is important to warp them as a 

* devtools
* python package manager

### Serving result as a REST API

#### Tools:

* Microservices framework (flask, flaskrestplus, FastAPI, plumber)
* API documentation (Swagger UI)
* Response and request model and validation (Pydentic, JSONSchema)

### Containerise the service and host in registry

#### Tools:

* Docker
* Docker registry

### Go live
Deployment using CI/CD pipeline

### Deployment in the development server

### Deployment in the staging server

### Measuring performance by load test

#### Tools:
* Locust
* Postman

### Deployment in the production server
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYwMzM5NzY3OCwxNzYzNjg2MywxNDAwND
QzMjc4LC04Mzg2MjE2MjcsMzIyNzA1OTAzLC03NDk4ODYxNjgs
LTE2MzU1ODE2NzYsMzg3MjE1MjU5LDE3Njk1MzI4NTQsMTIxNT
AwNzIyOSwtMjA5MTA5MDYwNCwtMjA4ODc0NjYxMl19
-->