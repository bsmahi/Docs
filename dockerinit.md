# Docker Init: New CLI command

Prior to Docker Desktop 4.19.0, we had to manually produce docker artifacts/assets; however, with the newest beta release, we can generate such artifacts/assets using the new command `docker init`. 

We will be able to initialise assets using the single cli command 'docker init'. The following assets are generated automatically when you run the command.
* Dockerfiles
* Docker Compose files
* `.dockerignore` files

The `docker init` command is extremely beneficial for developers who wish to experiment with Docker, learn how to containerize applications rapidly, and integrate Docker into their current projects. We can execute the command in the target project folder. Docker init will identify the project definitions and produce the assets required to start the project in Docker.

This command now supports the languages Go, Node, and Python, and the Docker development team is actively working on supporting new languages and frameworks like Java, Rust, and.NET.

> `docker init` command shouldn't be confused with the internally used `docker-init` executable, which is invoked by docker when utilizing the `-init` flag
> with the `docker init` command


