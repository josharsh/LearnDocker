# UNDERSTANDING CMD

Instructs the docker that as soon as this docker starts, execute the set of  commands following CMD. Basically, whatever under CMD will be executed as soon as the container starts


**Steps To Follow:**



*   Open the dockerFile
*   Inside the Dockerfile write **“FROM ubuntu”** (if not already there)
*   Write **“RUN sudo apt-update && apt-get install tree”**
*   Write **“CMD echo “I am learning Docker”**
*   Exit to the terminal 
*   Build the _dockerFile _using **docker build -t dockerFile*
*   Run the <em>dockerFile</em> using <strong>docker run --rm dockerFile</strong>

CODE: 

```
FROM ubuntu
RUN apt-get update
CMD echo "I am Learning Docker and Running a container"
```


Now, the echo statement is printed.  To run multiple instructions, come to docker file in your cmd command put a semicolon at the end of the first command the write the second command 

**E.g.**

```
CMD echo "Hello"; ls
```


Prints Hello and lists all files.

