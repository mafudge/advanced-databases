# Advanced Databases

A Lab environment for Big Data / NoSQL.

All of the joy of Bigdata/noSQL with little of the pain. Used in IST769 the advanced databases course.

[![DOI](https://zenodo.org/badge/445371462.svg)](https://zenodo.org/doi/10.5281/zenodo.10607506)

## Requirements

Before you gawk at the requirements, let's not forget that you're running big data systems on your computer :-)

- Windows OS 10 or higher / Linux / Mac OS with Intel Hardware virtualization
- Docker Desktop https://www.docker.com/products/docker-desktop/
- 16GB RAM
- 50GB free space for docker images and the datasets

**IF YOU DON'T MEET THESE REQUIREMENTS, YOU GOING TO HAVE A BAD EXPERIENCE IN THIS COURSE. PERIOD.**

##  Setting it up

Docker Desktop:
1. Download and install Docker Desktop https://www.docker.com/products/docker-desktop/
1. On Mac OS: Go to settings and make sure "Use Rosetta for x86/amd64 emulation on Apple Silicon" and "Use Virtualization Framework" are enabled.
1. Restart docker desktop
1. Make sure the docker engine is running.

Install Git:
1. Download and install git: https://git-scm.com/ 

Clone the this repository
1. Open a terminal to access the command-line interface of your operating system. Know the folder you are in! Its located in the command prompt
1. Clone this repository. From the terminal command line, type:  
`> git clone https://github.com/mafudge/advanced-databases`
1. Change into the cloned folder:  
`> cd advanced-databases`
Your command line prompt should now reflect the new folder e.g.:
`advanced-databases>`
1. Download the images used in the docker setup:  
`advanced-databases> docker-compose pull`
This will take a while, so be patient.
1. Create the containers, but don't start them:  
`advanced-databases> docker-compose up --no-start`

You are now ready to use the lab environment!

## Common Tasks

### Starting Services 

Use `docker-compose start <services>` to start the services you need. As a best practice, start only the services you need. The required services are listed in the problem set / lab instruction document.
For example, to start the `jupyter`, `drill` and `minio` services for the minio lab:
`$ docker-compose start jupyter drill minio`

### Stopping Services

Just like turning off the lights when you leave a room, when you are finished using the services, stop them:   
`$ docker-compose stop`  

You can also stop individual services:  
`$ docker-compose stop drill minio`

### Listing all available services

Can remember the names of all these services? Use this command to list all services in the `docker-compose.yml` file:  
`$ docker-compose config --services`

### Which services are running?

Need to know if a service is running? Or which port the service is available on? Try this:   

`$ docker-compose ps`   

The command will display which services are running and ports exposed to your host.

### Tips regarding ports

-Each database service uses its well known TCP port. For example Microsoft SQL Server is TCP/1433, Minio is TCP/9000.   
- Sample applications, such as `retwis` and `mongoapp` use ports in the 5xxx range.
- Admin web interfaces to databases like `rediscommander` or `mongoexpress` use ports in the 8xxx range.

### Checking the container logs

When things go wrong with a service (and you can count on that happening), you will need to check the container logs. For example to view the logs for the `zookeeper` service:   

`$ docker-compose logs zookeeper`

Searching the web for the error in the log usually gives you an indication as to what is going awry.


### Login Credentials for Services

Check the `docker-compose.yaml` file for the credentials for each service.


### Updating the git repository.

At times you may need to update the git repository. For example, if your instructor makes changes the content or examples. To get the latest updates:

`$ git pull`
