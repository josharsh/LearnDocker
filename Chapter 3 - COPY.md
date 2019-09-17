# Understanding COPY:

Command copy copies files and folder from local machine it puts them on running instance of the container so that container has access to them.

**Steps To Follow:**



*   Open the dockerFile
*   Inside the Dockerfile write** “FROM ubuntu” **(if not already there)
*   Write **“RUN sudo apt-update && apt-get install tree”**
*   Write **“COPY [Source] [Sink]”**
*   Exit to the terminal 
*   Build the _dockerFile _using **<code>docker build -t dockerFile</code></strong>
*   Run the <em>dockerFile</em> using <strong><code>docker run --rm dockerFile</code></strong>

<strong>Example:</strong>


```
FROM ubuntu
RUN apt-get update
COPY ./flask_apps /root/Flask
-------------------------------
docker build -t copy_docker
docker run -it --rm copy_docker
```


To copy flas_apps folder from local machine to root folder of container with the same name.

After the Container is started

Type: 


```
cd root
ls 
```


Flask-app is present and contains all the subfolders.
