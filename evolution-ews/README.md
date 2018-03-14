Evolution Docker container
==========================

Building it
-----------

Replace my_user in Dockerfile with your local username who uses the application.

Run:
```
docker build -t evolution .
```

Running it
----------

Replace my_user in the following command with the local username who uses the application.

Run:
```
docker run -ti --rm -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -v  /home/my_user/.Xauthority:/home/my_user/.Xauthority --net=host --pid=host --ipc=host evolution
```
