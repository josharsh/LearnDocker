Docker is just like an operating system for containers. Containers wrap up all dependencies to run a software. Irrespective of the presence of the dependencies on the local machine, dockers allow running the instance of containers which allow running the application needing those dependencies. 

Suppose on the Linux terminal we run a tree command which is not yet installed, it throws a not found error. But we can run the instance of a container which will allow running the tree command. 

**To Build a File:** <code> Docker build -t demo_tree . </code></strong>

**To run the instance**: `docker run -it demo_t `


```
[Note: -it flag means that the docker file is run in iterative mode]
```


**To run the instance only once: `Docker run -it --rm demo_tree`**


```
[--rm means the container will be deleted once it is exited from]
```



## From Keyword: 

Creates the underlying base image for building libraries

**Syntax:** FROM [base image name]

**E.g.:**         FROM ubuntu

**Steps To Follow:**



*   Create a folder using**<code> mkdir,</code></strong> navigate to it
*   Create a docker file using <strong><code>vi Dockerfile</code></strong>
*   Inside the Dockerfile write<strong> “FROM ubuntu”</strong>
*   Exit to the terminal 
*   Build the <em>dockerFile </em>using <strong><code>docker build -t dockerFile</code></strong>
*   Run the <em>dockerFile</em> using <strong><code>docker run --rm dockerFile</code></strong>


## Using RUN:

Suppose, the task is to get the tree package in the container which is not on the local machine.

RUN is used to run those commands which are to be executed while building the docker image

Since the underlying image is ubuntu, We want the packages updated and want to install package “tree”.

**Steps To Follow:**



*   Open the dockerFile
*   Inside the Dockerfile write**“FROM ubuntu”**(if not already there)
*   Write **“RUN sudo apt-update && apt-get install tree”**
*   Exit to the terminal 
*   Build the _dockerFile _using **<code>docker build -t dockerFile</code>**
*   Run the <em>dockerFile</em> using <strong><code>docker run --rm dockerFile</code></strong>

RUN apt- get update && apt-get install tree:

This will be executed using two different layers but the good practice is to use as fewer layers as possible.

Now ubuntu has been created as a base image and using the cache, the update has bee done and the tree has been installed on the instance of the running container. 

While the instance of the container is running type in:


```
cd /root
mkdir  -p parent/child1
touch parent/child1/index.html
ls
tree .

And it runs
Now, 
cd /root
mkdir  -p parent/child2
ls
tree .
```


Shows the directory structure. So the container has some files (package called tree) which were not in the local machine. So one can wrap up all the dependencies, files and packages which you want to run and deploy on any machine on which docker is installed. 

[Note: If the container is exited and the tree command is run from the local machine, it won’t run]
