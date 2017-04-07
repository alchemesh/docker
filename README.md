# docker
docker build files


These containers were built on the latest debian unstable version


These containers were built upon a private network for commincation between each one. Create and/or change the private network setting via the --net argument. There seems to be some issue with .Xauthority that I have yet to overcome and to make this work you have to run "xhost +x" from a command line. This will disable the access control. 
