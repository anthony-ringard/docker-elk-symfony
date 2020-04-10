docker-elk-symfony-5 :
==============

This is a stack for running Symfony 5 with ELK  into Docker containers using docker-compose tool.

# Installation

First, clone this repository.

Next,  add in your `/etc/hosts` file : 

```bash
127.0.0.1 symfony.local
```

Then, run:

```bash
$ make install 
```

```bash
$  sudo rm -rf symfony/*
```

In this container 
For traditional web application: 

```bash
$ make create-web
```

OR
 
microservice, console application or API
```bash
$ make create-skeleton
```

```bash
$ make stop 
```

```bash
$ make start 
```

You can visit your Symfony application on the following URL: `https://symfony.local:8080`


# How it works?

Here are the `docker-compose` built images:

* `database`: This is the MySQL database container (can be changed to postgresql or whatever in `docker-compose.yml` file),
* `php-fpm`: This is the PHP-FPM container including the application volume mounted on,
* `nginx`: This is the Nginx webserver container in which php volumes are mounted too,
* `elasticsearch`: This is the Elasticsearch server used to store our web server and application logs,
* `logstash`: This is the Logstash tool from Elastic Stack that allows to read logs and send them into our Elasticsearch server,
* `kibana`: This is the Kibana UI that is used to render logs and create beautiful dashboards. 


# Read logs

You can access Nginx and Symfony application logs in the following directories on your host machine:

* `logs/nginx`
* `logs/symfony`

# Use Kibana!

You can also use Kibana to visualize Nginx & Symfony logs by visiting `http://symfony.local:81`.
