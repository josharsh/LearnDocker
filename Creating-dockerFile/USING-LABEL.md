# UNDERSTANDING LABEL
Adding meta-data to docker image. The data can be looked up further (Credits, Licences or any kind of documents). 
* FROM ubuntu
* LABEL Description=”This is the Docker Image showing Label”
* docker build -t dockerfile .
* docker run --rm dockerfile
