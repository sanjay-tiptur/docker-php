docker-php
==========

Docker build files for testing the latest versions of PHPNG, HHVM and HippyVM

Installation
------------
In order to use the images you will need to have docker installed on your OS (https://www.docker.io/gettingstarted/#h_installation).
And you will need a clone of this repository

```
git clone https://github.com/slaff/docker-php.git
```


Building containers
-------------------
After that you have to build first the dev container and then the others. 
The following example demonstrates how to build the PHPNG container

First build the dev container

```
cd <path-to>/docker-php
cd Dev
sudo docker build -t dev .
```

After some hours you will have ready to use container that has almost everything needed for compiling and testing. 
Then build the PHPNG container

```
cd <path-to>/docker-php
cd PHPNG
sudo docker build -t phpng .
```

Running containers
------------------

If the build is ready you can check it by running it:

```
sudo docker run -a stdin -a stdout -a stderr -i -t phpng /bin/bash
```

This will show a prompt like this:
root@b5f338zyc9f65:/ #

The PHPNG compiled PHP is located under /home/dev/phpng
```
root@b5f338zyc9f65:/# cd /home/dev/phpng
```




