# UNDERSTANDING ENV
About environment variables when docker starts

```dockerfile
FROM ubuntu
RUN apt-get-update
ENV workdir=/root/  
WORKDIR ${workdir}  # WORKDIR /root/
# Created an environment variable for workdir
```