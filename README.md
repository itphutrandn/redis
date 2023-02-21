# REDIS NOTE

## Basic Command
![image](https://user-images.githubusercontent.com/71063877/220327920-738dc46b-442a-41f6-8543-30344981efc2.png)

### Commands for Handlings Strings
![image](https://user-images.githubusercontent.com/71063877/220328641-d3a25a05-23e3-43fb-89f9-eb2b6d9da460.png)

![image](https://user-images.githubusercontent.com/71063877/220328763-988af1ca-e08c-4138-a232-1cd70b2a0b99.png)

![image](https://user-images.githubusercontent.com/71063877/220328845-c624c47d-cc42-4b47-b00f-933581b1336c.png)

Please refer to the link bellow:
https://redis.io/commands/


## Installing on Windows
Below are instructions to run Redis locally on Windows.

You do not need to install Redis locally. You can complete the entire course using the Redis instance we already created on Redis Labs.  These instructions are only here incase you want to run a copy on your own machine.



First, a few notes:

There are two different versions of Redis.  They are called Redis and Redis Stack

Redis contains the core Redis database

Redis Stack contains the core Redis database and some additional modules that extend the functionality of Redis.

When we created an instance on Redis Labs, we got a copy of Redis Stack - it has these extra modules already installed.

Later sections in this course will require you to run Redis Stack, because we eventually use these extra modules

Installation Guide for Windows

These are the same install directions listed at https://redis.io/docs/stack/get-started/install/docker/



Install Docker Desktop for Windows from this page - https://docs.docker.com/desktop/windows/install/

At your terminal, run docker run -d --name redis-stack-server -p 6379:6379 redis/redis-stack-server:latest

To connect to your local Redis server and execute commands, run docker exec -it redis-stack-server redis-cli



If you want to connect the RBay e-commerce app to your local copy of Redis, update the .env file in the root project directory to the following:

REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_PW=


If you want to connect RBook to your local copy of Redis, you will need to run RBook locally. 

To run RBook locally, run npx rbook at your terminal.

Navigate to localhost:3050

Open the connection settings window

Enter a host of 'localhost'

Enter a port of 6379

Leave the password blank

When running RBook locally, any notebooks you create will be added to the folder you ran npx rbook in.
