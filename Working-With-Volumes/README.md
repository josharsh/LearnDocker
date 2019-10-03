# UNDERSTANDING VOLUMES:

To make the storage persistent in docker. 



*   docker run -it --name busybox_1 -v /data busybox

    // -v is used to add the volume

*   cd data
*   ls
*   touch test.txt
*   exit
*   docker run -t --name busybox_2 busybox
*   ls
*   //Even though the image is of same image, the file is not being displayed
*   exit
*   docker rm busybox_2
*   docker run -it --name busybox_2 --volume-from busybox_1 busybox
*   ls

    //Now the file is displayed inside the data folder.


This is how persistent storage is created in the docker. So 2 APIs in two container communicating with each other use volumes to share the data.

