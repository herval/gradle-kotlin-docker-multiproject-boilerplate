Multiproject Gradle + Kotlin + Docker Boilerplate
=================================================

A small boilerplate covering a bunch of things at the same time:

- Setting up a Gradle project with multi-artifact support (in our case, two executable Docker containers)

- Setting up a [Kotlin](https://kotlinlang.org/) project

- Building a [JVM container with Docker](https://github.com/bmuschko/gradle-docker-plugin). So you can put your interpreter inside your JVM inside your Docker container inside your Kubernetes inside your VPS inside your OS and be happy.


## Why?

- Multi-artifact projects are a must when dealing with a [monorepo](http://danluu.com/monorepo/)

- Docker containers are very easy to distribute, version, package, etc. It also simplifies orchestration (with [compose](https://docs.docker.com/compose/), making maintaining development environments a much smaller pain in the long run)

- Kotlin is awesome. There's not a lot of Kotlin code to see in this example, though, which is far less awesome.


## How?

- Clone this project

- To build the containers, run: `./gradlew foo:dockerBuildImage bar:dockerBuildImage`

- Run your containers with `docker run foo:latest` and `docker run bar:latest`


## Dependencies

You need to have Docker configured locally, as well as a working JDK (Java 7+). The `DOCKER_HOST`, `DOCKER_CERT_PATH` environment variables are also expected - these are set by `docker machine env` and will tell the Docker plugin where to build the images.

## Future improvements

- Move the copy+pasted `docker{}` directives to the top-level build.gradle