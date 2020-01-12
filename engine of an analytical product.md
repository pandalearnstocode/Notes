# A mental model for buliding engine of an analytical product

Curretly, I am working for The Nielsen Company in Product Development team. As a part of this role in past three years I have developed an mental model building engine of an analytical product. There is a huge amount of subjectivity involved here, but this thing works quite well for me. It may or may not be useful for everyone. In sub subsequent posts I will try to break down required part of this process but this post will be mostly an overview regarding the mental model of the analytical side of the product development. 

## The end to end workflow


![](https://pandalearnstocode.in/mental_model/a_mental_model_of_analytical_product_engine.png)

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

The formulated math problem has to be converted into a code in this section. This code will take a input from an existing dataset and will product result. While developing this code one must remember that this code will be converted late to an interactive app. So, this is important to make all the inputs dynamic and perform things in a small functions. These function should do less thing but should do that in an robust manner. 

### Communicate inital set of result for the data
After 

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxMDM3MTI3OTcsMTc2OTUzMjg1NCwxMj
E1MDA3MjI5LC0yMDkxMDkwNjA0LC0yMDg4NzQ2NjEyXX0=
-->