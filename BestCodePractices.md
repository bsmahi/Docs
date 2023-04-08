## Spring Boot Project Structure

Spring Boot applications should be designed in a modular project structure, with `controller` classes kept in the controller's package/module, `services` classes kept in the service module, `repository` classes kept in the repository module/package, and `configuration` classes kept in the config package/module.

### 1. Controllers should be simple and clean

* Controllers should just deal with the application's HTTP layer and should not perform any business logic.
* Replace with `@RequestMapping` with specific HTTP method:
    * For **GET** method use `@GetMapping`
    * For **POST** method use `@PostMapping`
    * For **DELETE** method use `@DeleteMapping`
* Controllers should be centred on a specific usecase or business capability.
* Method names should be properly defined and meaningful.

### 2. Services should focus on business logic

* Business capabilities/domains/use-cases should be the foundation of services. Application names should be descriptive, such as `CustomerService` or `RegistrationService`. Controllers and Services often have a 1:1 mapping.
* As a best pratice use Constructor Injection that keeps code clean does not allows us to create circular dependencies between beans.
* `Construction Injection` simplifies the process of instantiating and testing a class in a unit test by eliminating the requirement to specify an application environment.
* The Lombok project is a popular and frequently used Java library that is designed to reduce or eliminate boilerplate code. It helps you save time and effort. We may reduce space and improve the readability of the source code simply by utilising annotations.
* For Example, declare a final property of the interface type, and annotate the class using Project Lombok's `@RequiredArgsConstructor`, so that no need to hard code a constructor for that class.

```java

@Service
@RequiredArgsConstructor(onConstructor = @__{{ @Autowired }})
public class RegistrationServiceImpl implements RegistrationService {
  
  private final RegistrationRepository regisrationRepo;
  
  @Override
  @Transactional
  public Registration createRegistration(Registration registration) {
     return regisrationRepo.save(registration);
  }
  
}

```
### 3. Exception Handling

Spring Boot Application can handle exceptions at the controller or at the global level.

* Create `CustomizedResponseEntityExceptionHandler` class by extending `ResponseEntityExceptionHandler` and `@RestControllerAdvice` annotation, for example:

```java
@RestControllerAdvice
public class CustomizedResponseEntityExceptionHandler extends ResponseEntityExceptionHandler {

    @ExceptionHandler(Exception.class)
    public final ResponseEntity<ExceptionResponse> handleAllExceptions(Exception exception,
                                                                       WebRequest request) {
        ExceptionResponse exceptionResponse = new ExceptionResponse(LocalDateTime.now(), exception.getMessage(),
                request.getDescription(false));

        return new ResponseEntity<>(exceptionResponse, HttpStatus.INTERNAL_SERVER_ERROR);
    }

    @ExceptionHandler(UserNotFoundException.class)
    public final ResponseEntity<ExceptionResponse> handleUserNotFoundException(UserNotFoundException userNotFoundException,
                                                                               WebRequest request) {
        ExceptionResponse exceptionResponse = new ExceptionResponse(LocalDateTime.now(),
                userNotFoundException.getMessage(),
                request.getDescription(false));

        return new ResponseEntity<>(exceptionResponse, HttpStatus.NOT_FOUND);
    }

}
```
* Annotation controllers with `@ExceptionHandler(UserNotFoundException.class)`.
* Define all the exceptions in one class and can be used globally.

### 4. Project Lombok Library

* Use Lombok defined annotations effectively while creating Entity, Service implementation classes.

* `@Data`: Use it for DAOs, typically don't have a lot of logic and carry a great deal of boilerplate. It creates `getters, setters, toString, and equals/hashcode`.
* `@Builder`: It is useful when you have an object with many fields with the same type. Rather than having a constructor with many string fields, use the builder instead. We can use fluent api effectively
* By adding the `@Getter` and `@Setter` annotations, we told Lombok's to generate these for all the fields of the class. We can also refine the visibility of some properties, For example, if we want to keep our entities id field modifiers package or protected visible because they are expected to be read, but not explicitly set by application code, we can just use a finer grained `@Setter` for this particular field.
* `@NoArgsConstructor` will lead to a create an empty constructor generation.
* `@RequiredArgsConstructor` annotation, we'll get a constructor for all the final fields in the class, just as we declared them.
* `@NonNull` makes our constructor check for nullability and throw NullPointerException accordingly.

