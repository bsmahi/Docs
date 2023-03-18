## My Journey with Technologies

I've mostly worked on `Java, J2EE, Spring Boot, Microservices, Spring Framework, WebServices (SOAP & REST), Spring Security (implemented using Basic, Certificate-based Authentication, JWT, OAuth2, and SSO), Spring Boot and Microservices`, Container technologies during the last several years (Docker).
In addition, unit test cases were built utilising the Junit and mockito frameworks.  We utilised REST Assured for integration testing, which is more of a domain-specific language for testing and validating Restful APIs. Have substantial experience with `Maven, Git, and Github`. 

In my projects, I employed Java8 technologies such as `lambda expressions, stream API, method reference, optional, and functional interfaces`, which allowed us to write code more declaratively rather than imperatively.
The Lambda expression and stream API are useful for retrieving a succession of items from diverse collections. Furthermore, we may change or obtain the final collection using the high-order techniques filter-map (which works as an intermediate operation) and reduce (which works as a terminal action).

For example, in the code below, we may turn the array into a list, filtering out any null values and avoiding null pointer errors while obtaining members from the list. It also employs the notion of a fluid API, which employs the premise of the chain of responsibility pattern.

```java
public List<SampleArray> getRecordsDetails() {
 
    return Optional.ofNullable(getSampleArray())
                          .map(Stream::of) // used method reference concept here
                          .orElseGet(Stream::empty) // used method reference concept here
                          .filter(Objects::nonNull) // filter out all null values from the collection
                          .collect(ImmutableList.toImmutableList()); // used ImmutableCollection

}

```
From the java.util. We utilised interfaces such as `Function, Consumer, Predicate, BiConsumer, and Supplier` in the Function package.

We utilised the flatMap technique to combine several list entries into a single list. We utilised the fluent API's distinct() function to retrieve a single list with duplicates for a frontend application.

For example: if we want to remove the duplicate phone number from the list of list.

```java
phoneNumberDetails.stream()
  .flatMap(Collection::stream)
  .distinct()
  .collect(Collectors.toList()) 

 ```
We also used Basic Java concepts including String functions, OOPs, Collections framework, and Exception Handling.

**Immutables**: To construct thread-safe, serialising and deserializing objects (using JSON Serialization), we utilised the Immutables library, which acts as a Java processor and as a building pattern (by default, builders will generate for each implementation class). For the majority of the models or POJOs, we leveraged the Java Processor features to generate value objects. During build time, we will be able to generate Immutable value objects. As an example:

```java
@Value.Immutable
@JsonSerialize(as = ImmutableProposedRecord.class)
@JsonDeserialize(as = ImmutableProposedRecord.class)
public interface ProposedRecord {

}

```
**Lombok**: We also utilised the Lombok plugin to generate getter, setter, function toString() { [native code] }, and Constructors inside POJO or Entity classes by leveraging the Lombok library's annotation capabilities. It will also cut down on the amount of lines.

Right now, I am using concept of `record` for creating final and immutable classes. Recently, all `javax` package migrated to `jakarta` package.

## Spring Framework & Spring Boot

We have included `Core Spring, Spring Data JPA, Spring Security, and Spring Batch` capabilities in the Spring Framework. I'll show you how in the next section:

**Core Spring**: Techniques like as Dependency Injection (DI), Inversion of Control (IoC), and Aspect-Oriented Programming (AOP) are used to generate objects or beans that may be injected during runtime.
Spring Container aids in the preservation of the bean life cycle. We have widely exploited these capabilities to develop a loosely linked design for any online application.

We have created bean(s) using XML configuration or annotation-based. I have started crafting beans using XML tags during my early days of programming. 
Later on, have used annotated-based, the most sophisticated one and less error-prone.

We have used annotations below annotations (in fact many more) in my projects:

`@Bean`: This is used to define a bean that was configured in the configuration class so that when the application begins, it would load into a spring container or an IoC container.

`@Autowired`: used for injecting an object through a function Object() { [native code] } or a setter.

During the application's bootstrapping, `@Configuration` is used to create @Bean methods, bootstrap data sources, environment variables, and ResourceBundle characteristics for Internationalization.

When many beans are qualified to autowire a single-valued dependence, `@Primary` is used to grant priority.

`@Qualifier` is generally used in conjunction with the @Bean annotation to handle autowiring conflicts when there are numerous beans of the same type.

`@Value` is used to extract attributes from ResourceBundle based on profile (dev, staging, and prod) and inject values into configuration variables.

**Spring MVC**: We implemented the majority of the web application using the MVC design pattern, with features such as `DispatcherServlet` (specified in web.xml) acting as a front controller, request processing, and dispatching/forwarding the request to suitable controllers.

## Spring Transaction Management:

We have achieved comprehensive transaction management for commit and rollback operations at a higher abstraction level without utilising any transaction methods, just by using the `@Transactional` annotation and configuring with the AOP methodology.

To eliminate dirty reads and phantom reads during transactions, we employed propagation and isolation level ideas, as well as the `@Transaction` annotation.
## Spring Security:
For authentication, we utilised Spring Security Module's BasicAuthentication (base64(username: password)).

For both authentication and authorisation, we utilised LDAP Authentication.
Subsequently, for authentication, token-based authentication utilising `JWT` and `OAuth2` is used. When working on SOAP web services, we also employed certificate-based authentication (public and private key), with the certificates exchanging during consumption. After certificate-based authentication is complete, a second tunnel will be opened for the remainder of the requests. We implemented SSO by use certificate-based authentication. RESTful APIs have utilised the same authentication and authorisation.

## WebServices:

We have created APIs for connecting between client and server that use SOAP and RESTful web services.
For SOAP web services, we used JAX-WS technology (which is more API driven) (message-oriented web services). For complicated and basic kinds, we utilised XSD (XML Schema Definition). Essentially, they are things that we define using XML tags. We will configure WSDL using these XSDs. The majority of the SOAP web services that I constructed through consuming SOAP web services.
In pom.xml, we will set the WSDL plugin to generate objects (schema-to-java).

REST APIs are used to develop APIs that leverage CRUD operations in conjunction with the Spring Data JPA module. We have a dataGrid in my frontend application that requires pagination and sorting. We don't need to develop a DAO layer because the JPARepository (which implements CRUDRepository) interface provides a lot of predefined methods and implementation. We utilised HTTP method mappings (`@GetMapping, @PostMapping, @PutMapping, @DeleteMapping, and @PatchMapping`) instead of `@RequestMapping`, which has more defining freedom.
For producing queries based on the JPA Criteria API, we utilised `@JpaSpecificationExecutor`. For instance, findByStartDateAndEndDate will build a query using the findBycolumn name>And/Or/Likecolumn> technique.

We built the majority of the application with a high-level API RestTemplate (which is based on an HTTP client) for interaction with other APIs. The Resttemplate class has approximately 50 methods, the majority of which are overloaded many times and are mostly used for synchronous communication.

We've been utilising the Spring WebClient class for synchronous and asynchronous communication in a few applications already.

The majority of the APIs we've designed used JSON as the request and response format. We kept the application's package structure the same in both Spring and Spring Boot applications: controllers, models, services, service.impl, config, and so on.
This allows us to keep our code clean and modular.

## Spring Boot using Microservices:

During the past five years, the majority of standalone apps and monolithic application migrations have been developed with the Spring Boot framework, which includes capabilities such as Autoconfiguration, Externalized Configuration, Transitive Dependency Management, and Actuator, among others. And we've utilised it for both greenfield and brownfield construction.

We used the spring boot starts functionality to address dependency management for the many version conflicts, allowing us to have a clean pom.xml.

To transition a monolithic programme to a microservices application, Microservices architectural design patterns were used. We separated the frontend, backend application, and externalised configuration (through GitHub repository) and developed them independently so that we could utilise alternative CI/CD pipelines. Spring Cloud Bus capabilities that employ the message broker architecture to disseminate centralised settings to all environments.

Other Spring Boot projects include Eureka Naming Server (Service Registry), API Gateway (Service Discovery), and Spring Cloud (Circuit Breaker, Hystrix Command and recently replaced with Resilience4j).

We utilised Feign and Ribbon Client (which is redundant if we use Feign client) to communicate with other microservices. I recently began working with HTTP Interfaces.

Have an exposure of Container technologies like `Docker and Kubernetes(K8s)` and `Apache Kafka`

## Maven, Git, Github, Bitbucket and Gitlab:

The Maven build tool is used for dependency management in the majority of projects.

I have worked with Git (CLI and IDE integrated), Github, Bitbucket, and Gitlab across the DevOps life cycle. The feature branch idea was used for the majority of the project, and following code review, we would merge to the master (now main) branch.

For jar optimization, we utilised spring-boot maven plugins such as thin-layout and shading.

## Testing Frameworks:

I'll be utilising Junit (both Junit4 and Junit5) and Mockito as a mocking framework to write unit test cases.

RestAssured, which does end-to-end testing, will be used to write Integrated test cases.

To obtain comprehensive code coverage based on unit and integration testing, I utilised the Jacoco plugin and SonarQube.

## Cloud Experience

I've been working on Amazon for two years, using various services like as S3, CloudFormation, SQS, SNS, Secrets Manager, Systems Manager, and Cloudwatch.

Thanks,
Mahendra
