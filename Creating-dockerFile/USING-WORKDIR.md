# Understanding Workdir 

Working directory specifies a default directory in the docker image to perform certain instruction. The use case can be , we have a set of instructions to execute some commands inside a particular directory. It won’t be convenient to use the particular path to the directory every time for each command to be executed. 

To set a default working directory for all such instructions is done using this command

vi dockerFile

FROM UBUNTU

//Few files in one dir, few in another

RUN touch  /root/testfile.txt

RUN touch /root/testfile2.txt

RUN touch /root/testfile3.txt

// To create more folders

RUN mkdir-p root/testFolder/child-1

RUN mkdir-p root/testFolder/child-2

/* Tiresome work */

Alternatively

FROM ubuntu

WORKDIR /root/

RUN touch ./textfile1.txt

RUN touch ./textfile2.txt

RUN mkdir ./newFolder/childFolder-1

WORKDIR ./root/newFolder/child-Folder-1

// Now working directory is /root/newFolder/child-Folder-1

RUN touch hello.txt

So, workdir basically puts you onto the directory where you want to be when the docker starts
