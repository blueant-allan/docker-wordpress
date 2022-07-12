## Dockerfile development configuration

For Wordpress using Ubuntu as base image. Different ubuntu version and php support will be available on branch

Branch naming conventions would be the following:

Example:
	Ubuntu 22.04
	Nginx 
	PHP-FPM version 8.1
	Branch name: u22.04-ngx1.z.y-p8.1

Stack
* Nginx
* PHP-FPM 
* PHP version 8.1

Loaded PHP Extensions

* Mysql
* Intl
* Mbstring
* Zip
* Xml
* Sqlite3

Home directory is set to var/www/html

## Compile the docker file

```
docker build -t u22.04-ngx1.z.y-p8.1-image -f Dockerfile.dev .
```

## Create instance of the container

```
docker run -p 8080:80 -dit --name conainer_name.web --mount type=bind,source="$(pwd)",target=/var/www/html u22.04-ngx1.z.y-p8.1-image
```


## Manage the container

```
docker exec -it conainer_name.web bash
```


## Usage

1. Build the dockerfile configuration and create a container for it.

2. Now that you have your container setup, you can access it via

```
docker exec -it <project-name> bash	
```

3. You should be able to load your web-application from your browser with the port you incidated above. Example: http://localhost:8080


