# UNDERSTANDING STOPSIGNAL

To stop a running docker STOPSIGNAL is used. 



*   FROM ubuntu
*   RUN apt-update
*   STOPSIGNAL SIGKILL
*   docker build -t dockerfile .
*   docker run -t --rm dockerfile stop_file
