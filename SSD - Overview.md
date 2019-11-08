# Statistical Software Development:

There is no need to explain the importance of an statistical software at the present. Be it a package/library in any language or be it product in a organization every thing falls under statistical product if the core of the product is driven by the statistical solution of the software. 

The key different between a product and a library is the product comes with many other complex things like UI, Backend and DevOps, Database where as a package or a library is mostly independet of these sort of things. Here I will try to explain the analytical engine side of things which mainly does the computation part of this problem which is somewhat similar for a product or a library. 


## What is analytical engine:

By the analytical engine word here I want to mean that the piece of code which takes input from the user be it in the form of a data file or in some other form. For example if we click some button from the UI of a product or we define a model type from IDE both of them are considered to be a user input. The combination of data on which these operations are being performed and user choice (like choice of a model is linear) constitures the input parameters of a engine. 

The task of the engine is to compute some things on the basis of this user choice and be consistent in its result in terms of statistical relevance when these input changes. Here we make an assumption that there will be a structure to the input which goes into the engine. We may or may not know then exact format or schema of the input but we need to make the engine as accomo

## What is REST?

## How to design an Analytical Engine:

### Design:

#### Validate:
##### Data location:
##### Data fields:
##### Data values:
* Categorical
* Numerical
#### Parse:
##### Apply schema:
##### After schema:
#### Impute:
##### Impute numerical:
##### Impute categorical:
#### Transform:
##### Transformation possible in present data structure:
##### Sorting of data of data in columns and rows according to requirment
##### Grouping of data according to requirments
#### Restructure input:
##### Nest to flat
##### Dataframe to array or vectors
##### Flat to nd array or generalised data structure
#### Compute:
##### Raw computation by function
##### Integration of function
##### Documentation of function
##### Unit test of functions
##### Property based test of functions
##### Development of error handeling
#### Restructure output:
##### Desired output format keeping data suffiency
#### Response:
##### Validate response
##### Response
#### Code coverage
#### Load and preformance testing
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEzODMzMDAxNSw2OTk1MTYzOThdfQ==
-->