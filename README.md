# Gallery — Config Repository

Externalized configuration for the [Gallery microservices](https://github.com/Stefan015/Gallery-microservices)
system. This repository is the Git-backed source that the **Spring Cloud Config Server**
serves to each service at startup.

## How it works

Each service fetches its configuration from the config server by name. A file like
`catalog-service.properties` here becomes the configuration for `catalog-service`; the
`*-docker.properties` variants hold the values used when running under Docker Compose.

```
service starts ──▶ asks config-server for "<service-name>"
config-server  ──▶ reads <service-name>.properties from this repo ──▶ returns it
```
