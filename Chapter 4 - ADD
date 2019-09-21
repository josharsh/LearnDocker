# UNDERSTANDING ADD

Add is similar to copy but with more functionality like it extracts the content of compressed files and puts it in docker image and has the ability to download and extract files

Navigate to a folder with tar compressed file. 

Vi dockerFile


```
FROM ubuntu 
RUN apt-get update
ADD ./Harsh_apps.tar.gz /root/ 
// Harsh_apps will be copied to root after exracting 
CMD if test -d "/root/Harsh_apps; then echo "Success"; fi
```

exit 

**Build:** `docker build -t dockerFile`

**Run:** `docker build -t dockerFile--rm dockerFile`


```
// The message "Success" is printed
```


Run in Interactive Mode: docker run --rm add_docker ls/root/Harsh_apps/  to see if Harsh_apps has some folder inside it.

In place of “Harsh_apps.tar.gz”, a URL can also be given.

<span style="text-decoration:underline;">It is not recommended, the best practices it to use wget or curl and then move it to the required destination, Go with RUN to use wget and extract things.</span>
