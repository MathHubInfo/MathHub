# MathHub

The new version of the MathHub System, managed with Docker Compose. 

It consists of several containers, which can roughly be split into two groups:

- Management Containers
    - [v2tec/watchtower](https://github.com/v2tec/watchtower) -- automatic updates
    - [portainer/portainer](https://github.com/portainer/portainer) - to manage docker containers
- MathHub System
    - [mathhub/compositor](https://github.com/MathHubInfo/Compositor) - to delegate access to the containers below
    - [mathhub/frontend](https://github.com/MathHubInfo/Frontend) - to provide a frontend for MathHub
    - [mathhub/letitgo](https://github.com/MathHubInfo/LetIt.Go) - to provide frontend configuration for MathHub
    - [mathhub/news](https://github.com/MathHubInfo/News) - to provide a news ticker for MathHub
    - [kwarc/mmt](https://github.com/Uniformal/MMT) - to provide a backend for MathHub
    - [mathhub/admin](https://github.com/MathHubInfo/Admin) - to provide an Admin interface

## Configuration

This repository supports both a local and production setup. 
All configuration is done via env files. 

These can be interactively generated using the configure script:

```bash
./configure
```

This script re-uses existing configuration if available. 
Furthermore, for a local setup, it is safe to accept all defaults. 

**WARNING:** Always shut down MathHub before re-running the configuration script. 

## Starting and Stopping

**WARNING:** Do not attempt to run any of these commands without having gone through the configure script first. 

After having configured appropriatly, you can start the setup as follows:

```bash 
# to start all the containers
docker-compose up -d

# to create an initial admin user
docker-compose exec admin python manage.py createsuperuser

# to stop the containers, but keep state
docker-compose down

# to stop all containers and remove all state
docker-compose down -v
```

## License

Licensed under AGPL 3.0. 