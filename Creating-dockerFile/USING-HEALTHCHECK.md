# UNDERSTANDING HEALTHCHECK

Healthcheck is a docker command which is used to check the application resources. 



*   FROM ubuntu
*   RUN apt-update
*   HEALTHCHECK --interval=5s --timeout=3s --retries=2 CMD cd ./label_cd

    // The command cd should give some output within 3 seconds and if if does not give output in two retries then the docker is exit with code 1

*   docker build -t dockerfile .
*   docker run --rm dockerfile
*   //Inside Docker now
*   Check state in JSON file
