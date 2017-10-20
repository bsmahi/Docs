Difference between ROLE_ANONYMOUS and IS_AUTHENTICATED_ANONMOUSLY

Both are effectively the samething when defining access controls. AuthenticatedVoter uses an AuthenticationTrustResolver to process this 
particular configuration attribute and grant access to anonymous users. 
The AuthenticatedVoter approach is more powerful, since it allows you to differentiate between anonymous, rememberme and fully-authenticated
users. If you don't need this functionality though, then you can stick with ROLE_ANONYMOUS, which will be processed by Spring Security's standard
RoleVoter.

https://docs.spring.io/spring-security/site/docs/3.0.x/reference/anonymous.html

@RequestParam

  1. One of the way to sending data from the Browser to the Server. Using @RequestParam or request parameter to send the data
  For Example: http://localhost:8080/rest/student/add?name=SteveJobs&subject=AppleComputers

@RequestBody

1. Another way is @RequestBody generally this annotation is used for updating any details. We will pass JSON Object, Spring will use 
Jackson to map that respective defined class automatically.

code snippet : @RequestBody Student student object

We need to set the Content-Type to application/json and Send the JSON as the request body.

@PathVariable

Another way is send the data as part of the URL itself. Spring provides @PathVariable annotation for this. Generally we will
use this delete any details

For example: http://localhost:8080/rest/student/delete/{id}

Actuator -- Actuator is a very helpful library which provides runtime details of our application. To start with, we can find
whether our App and all of its components(Like DB, Cache, MQ etc) are up or down. 
It also shows all the services available for an application. Additonally all properties, including server details, dump and many other
details are easily available is your browser using Actuator.

http://localhost:8080/health -- will give details about server or free space whether it is up or down
http://localhost:8080/mappings -- will give all the Request Mappings.

You can customize actuator to display or restrict information that should/shouldn’t be available. For getting the full list, check this URL.

URL	Desc
env -->	Exposes properties from Spring’s ConfigurableEnvironment.
beans -->	Displays a complete list of all the Spring beans in your application.
configprops-->	Displays a collated list of all @ConfigurationProperties.
dump-->	Performs a thread dump.
health-->	Shows application health information (when the application is secure, a simple ‘status’ when accessed over an unauthenticated connection or full message details when authenticated).
logfile-->	Returns the contents of the logfile (if logging.file or logging.path properties have been set). Only available via MVC. Supports the use of the HTTP Range header to retrieve part of the log file’s content.
metrics-->	Shows ‘metrics’ information for the current application.
mappings-->	Displays a collated list of all @RequestMapping paths.
trace-->	Displays trace information (by default the last few HTTP requests).
