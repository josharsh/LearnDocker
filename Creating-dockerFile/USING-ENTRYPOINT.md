# UNDERSTANDING ENTRYPOINT
Used to run the instructions when docker starts. The difference between CMD and ENTRYPOINT is that the instructions written in ENTRYPOINT can not be overridden.
STEPS TO FOLLOW:
*ENTRYPOINT ls
*docker build -t dockerfile .
*docker run --rm dockefile

## To Check If Overriding Works?
After Building run any other command other than the one given under ENTRYPOINT.
