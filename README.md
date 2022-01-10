# advanced-databases

Lab environment for the Advanced Databases / Hadoop / NoSQL course


## Requirements

Before you gawk at the requirements, let's not forget that you're running big data systems on your computer :-)

- Windows / Linux / Mac with Intel Hardware virtualization
- Docker Desktop 4.3 or on Linux Docker 20.10 
- 16GB RAM
- 40GB free space for docker images and the datasets

## Before You Begin

There's one-time prep you must do after cloning the git repository.  Have dinner or go for a walk, as it can take some time to clone the images.

Download the images:     
`$ docker-compose pull`  

Create the services:  
`$ docker-compose create`

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




