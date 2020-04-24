# microservice-config

Naming a Properties File Stored in Git Repo

Properties files served by Spring Cloud Config Server can be names in few different ways:

application.properties – is a default file property file name,
{microservice-application-name}.properties – if a property file which is stored in Git repo is named after the Microservice name, then properties loaded from this file will have a higher priority. The value of {microservice-application-name} you will need to look up in an application.properties file of a Microservice which is specified with a property spring.application.name=
{microservice-application-name}-{profile name}.properties – if a Spring Boot Profile is used in the name of the file and that profile name is set as active then a file name with {application-name} and a {profile name} in it, will have even higher priority.


If this key is available in a property file loaded by a Config Server then it will be assigned to a String variable “token” defined in the above Controller class. If the key is not found in the property file loaded from a Config Server application, then its value will be read from a local application.properties file.
 
Values loaded by Config Server always have higher priority. Which means that even if your Config Client application also has its own application.properties file with a key token.secret defied, the value loaded for the same key from a Config Server will be used.
