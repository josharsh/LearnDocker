# Networking in Docker
Docker takes care of the networking aspects so that the containers can communicate with other containers and also with the Docker Host.

# Understanding Expose

To expose the port number of container to the physical host. The physical host will b e connected to the internal port of the container. The application will be running on the container



*   FROM python:3-onbuild //picks requirements.txt and installs packages from it.
*   COPY ./init.py /root/init.py

    The init file is actually a file created using flask and has the port number 5000 in it

*   EXPOSE 5000
*   ENTRYPOINT python /root/init.py
*   Save and Exit
*   docker build -t expose_build .
*   docker run --rm -p 8080::5000 expose_docker

    8080 is the external port which maps to 5000 port.


    Go to browser and connect to the container. 



# Understanding Networking:

Create a network in host to run the container.

The idea is to have the range of IP address so that they can be assigned to the containers. For this CIDR will be used. CIDR is Classless Inter Domain Routing. A private subnet will be created.  



*   docker network  create--subnet [CIDR(172.20.0.0/16)] harsNetwork

    To create a subnet. First 16 bits are reserved for network address and rest 16 for host addresses. The CIDR network address has to be of 10.0.0 or 196.0.0 type because only private addresses can be used. 

*   docker network ls

    Shows the networks created 

*   docker run -it app_container --ip 172.28.0.10 --harshNetwork
*   Run ipcofig inside container 
*   Come to host machine and ping the container using ping 172.28.0.10
