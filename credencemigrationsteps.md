# Migrate Struts to Spring Boot Application


## Frontend

* Decouple all jsp's and create React application as a microfrontend.
* Because the existing struts application has a large number of photos, we must store them in a content delivery network (CDN), which will reduce the load on the real application.
* Build components that are based on the service.
* Clearly define the dependencies in the `package.json` file.
* Clearly define the environment file and declare backend URL there.
* Build a shared javascript file and specify the methods that will be utilised throughout the application.
* Delete the inline CSS code and replace it with one from an external file.

## Backend
* Use `JDK Version of 17`, `Spring Boot 3.0.4` version
* Instead of constructing a single Spring Boot application, let's divide each service into its own microservice (based on bounded context) and call it inside.
* Let's create containerize each of the microservice as docker image and use `docker-compose`. 
* By constructing a `spring cloud config server`, we can externalise all application related properties and load them.
* We must develop an api-gateway (Spring Cloud Gateway) microservice to address cross-cutting concerns such as `loadbalancer, security, monitoring/metrics`, and robustness.
* We must develop a naming-server/service registry(`Eureka Server`) and define in a REST service, which registers itself at the registry (`Eureka Client`).
* We must incorporate `Resilience4j` core modules to handle resilience. 
* We must interact with `@RestControllerAdvice` utilising custom exception handling for exception handling.
* We must implement logging, monitoring/metrics using tools `prometheus, zipkin, and micrometer`.
* Let's externalize mysql as docker image used in docker compose.
