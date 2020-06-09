# BaseProject

Base Project to work with Docker, NginX, Python, MongoDB

# Schema

![alt text](https://github.com/wborbajr/BaseProject/blob/master/schema/Docker.png)

# Base (buildbase)

It is an alpine Linux 3.9, configured with time zone and locale and all  extras unnecessary files are removed, provides a light base image.

# Database

From buildbase, mongodb it is installed and configured.

# API 

From buildbase, Python + FastAPI and another other packages are installed.

# Web 

From buildbase, the following packages are installed, LightHTTPd + VUE.
