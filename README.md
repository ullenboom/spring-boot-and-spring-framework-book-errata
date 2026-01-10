# Errata for *Spring Boot 3 and Spring Framework 6*

This repository collects and tracks errors, corrections, and clarifications for my book *Spring Boot 3 and Spring Framework 6*.

## 📚 Book Details  
- **Title:** *Spring Boot 3 and Spring Framework 6: Build Scalable, Modern Java Applications with Spring and Spring Boot—From Fundamentals to Advanced Techniques*  
- **Author:** Christian Ullenboom  
- **Publisher:** Rheinwerk Computing  
- **ISBN:** 978-1493224753  

## 📖 About this Page
Despite my best efforts, some typos, logical inconsistencies, or misplaced semicolons may have found their way into my book. This repository serves as a centralized place to report and document any inaccuracies, typos, or clarifications.

## 📌 How to Report an Issue  
Found a mistake in the book? Simply open an issue:
- Provide the **chapter**, **section, or code listing**, and a **clear description** of the issue.  
- If possible, suggest a correction or clarification.  

## 📝 Errata List  

### Chapter 1: Introduction  

#### More Spring Boot Application Starters

- ❌ An overview of all starters is provided at https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#using-boot-starter.   
- ✅ An overview of all starters is provided at https://docs.spring.io/spring-boot/reference/using/build-systems.html#using.build-systems.starters. 

#### Getting Started with Configurations and Logging

- ❌ The Initializr creates various documents, among them the application.properties file **, which is empty by default**.
- ✅ The Initializr creates various documents, among them the application.properties file.

####	Summary

- ❌ You can also do this via the Spring Boot CLI, a command-line tool, but this is rarely used in practice, so I refer you to the reference documentation at https://docs.spring.io/spring-boot/docs/current/reference/html/cli.html.
- ✅ You can also do this via the Spring Boot CLI, a command-line tool, but this is rarely used in practice, so I refer you to the reference documentation at **https://docs.spring.io/spring-boot/cli/index.html**.


### Chapter 2: Containers for Spring-Managed Beans

#### AwtBicubicThumbnail for Thumbnails

- ❌ shell:>upload-photo 'C:/Users/User/Desktop/neues-bild.jpg'
- ✅ shell:>upload-photo 'C:/Users/User/Desktop/**new-image**.jpg'

#### @DependsOn

- ❌ @DependsOn( “fileSystem” )
- ✅ @DependsOn( "fileSystem" )

#### Global Delayed Initialization

- ❌ SpringApplicationBuilder**s**: lazyInitialization(true)
- ✅ SpringApplicationBuilder: lazyInitialization(true)

#### Aware Interfaces *

- ❌ Then, when we implement the interface, we only need to override the setBean(…) method.
- ✅ Then, when we implement the interface, we only need to override the setBean**Name**(…) method.

#### @Conditional and Condition

- ❌ Here’s afictional example:
- ✅ Here’s **a** fictional example:

#### 2.10.1 @Conditional and Condition

- ❌ We can put this class, which implements `@Condition`, to a component definition:
- ✅ We can put this class, which implements `Condition`, to a component definition:


### Chapter 3: Selected Modules of the Spring Framework


#### PropertyResolver and Environment

- ❌ So the property com.tutego.number**s**-of-seminars is converted to an Integer.
- ✅ So the property com.tutego.number-of-seminars is converted to an Integer.

#### Task: Introduction of a Configuration Class

- ❌ The initialization with filesystem = new Filesystem() is important because if you inject a Date4uProperties object and call getTutego().getMinimumFreeDiskSpace() on it, there should be no NullPointerExcep-tion.
- ✅ The initialization with filesystem = new Filesystem() is important because if you inject a Date4uProperties object and call getTutego().**getFilesystem()** on it, there should be no NullPointerException.

#### Search Locations for Configuration Files

- ❌ Resolution: The first file isn’t considered at all because it’s only searched in direct subdirectories of the config directory. The same applies to config/http/s/application.properties be-cause this is too “far away” and is also not read. A look at the list shows that file:/config/*/ has the highest priority, which, in our case, is config/http/application.properties. Consequently, com.tutego.homepage is equal to http://tute.com/. What is normally in application.properties has the weakest priority of all. That is, the entry isn’t considered at all, and everything else is more important.
- ✅ Resolution: We can solve this in two steps. First, we can disregard config/http/s/application.properties because Spring Boot only looks in the immediate subdirectories of the config directory. This means the file is “too deep” and won't be read. The remaining three files are read, but their priority determines which one is used. A closer look reveals that file:/config/*/ has the highest priority, which in our case refers to config/http/application.properties. As a result, com.tutego.homepage will be set to http://tutego.de/. The values in application.properties would have the lowest priority of all.

#### Implement Exception Classes ExitCodeGenerator

- ❌ throw new InsufficientDiskSpaceException( “Was only 2 KiB" );
- ✅ throw new InsufficientDiskSpaceException( "Was only 2 KiB" );

#### Annotation @SpringBootTest

- ❌ By default, all components from the main configuration are recognized, and instances can be injected into the test class with @Autowiring.
- ✅ By default, all components from the main configuration are recognized, and instances can be injected into the test class with **@Autowired**.


### Chapter 4: Selected Proxies

(No known issues)


### Chapter 5: Connecting to Relational Databases

#### Different Pooled Connection Implementations

- ❌ Spring Boot evaluates dozens of configuration properties; the reference documenta-tion lists them at https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#appendix.application-properties.data.
- ✅ Spring Boot evaluates dozens of configuration properties; the reference documenta-tion lists them at **https://docs.spring.io/spring-boot/appendix/application-properties/index.html#appendix.application-properties.data**.

- ❌ In principle, other implementations can be used, and auto-configuration supports oth-er connection pool implementations; details can be found at https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#data.sql.datasource.connection-pool.
- ✅ In principle, other implementations can be used, and auto-configuration supports oth-er connection pool implementations; details can be found at **https://docs.spring.io/spring-boot/reference/data/sql.html#data.sql.datasource.connection-pool**.

#### DataSourceUtils *

- ❌ With a DataSoure in hand, a JDBC connection can be established with getConnection(), but this introduces two problems.
- ✅ With a DataSour**c**e in hand, a JDBC connection can be established with getConnection(), but this introduces two problems.


#### ResultSetExtractor

- ❌ With a RowMapper and RowCallBackHandler, the JbcTemplate iterates over the ResultSet for us, and we can process the row.
- ✅ With a RowMapper and RowCallBackHandler, the J**d**bcTemplate iterates over the ResultSet for us, and we can process the row.


### Chapter 6: Jakarta Persistence with Spring

#### Build and Submit JPQL Queries with createQuery(…)

- ❌ The result is an object of type TypeQuery, which is generically typed with our Profile.
- ✅ The result is an object of type Type**d**Query, which is generically typed with our Profile.

#### Stream Return

- ❌ The result is a typed stream in the case of a TypeQuery.
- ✅ The result is a typed stream in the case of a Type**d**Query.

#### Automatic Dirty Checking

- ❌ With a closed EnitiyManger or a detached object that isn’t in context, no changes are detected.
- ✅ With a closed EnitiyMan**a**ger or a detached object that isn’t in context, no changes are detected.

#### @Basic and @Transient

- ❌ But this is better done via @Colum.
- ✅ But this is better done via @Colum**n**.

#### Shared @Embeddable and @AttributeOveride

- ❌ Shared @Embeddable and @AttributeOveride
- ✅ Shared @Embeddable and @AttributeOver**r**ide

#### JPQL with Association

✅ SQL has to be:

```sql
select
    u1_0.id,
    u1_0.email,
    u1_0.password,
    u1_0.profile_fk 
from
    unicorn u1_0 
join
    profile p1_0 
        on p1_0.id=u1_0.profile_fk 
where
    p1_0.gender=2
```


### Chapter 7: Spring Data JPA

#### Sort Type

- ❌ The simplest way is to pass the name of the persistent attribute to the of(…) method.
- ✅ The simplest way is to pass the name of the persistent attribute to the **by**(…) method.

#### @Query with JPQL Projection

- ❌  "SELECT p.id A id,p.nickname as nickname FROM Profile p WHERE id=:id"
- ✅  "SELECT p.id A**S** id,p.nickname AS nickname FROM Profile p WHERE id=:id"

#### JpaSort

- ❌ The JpaSort class extends Sort and inherits the of(…) method, so JpaSort.of(…) also returns only one Sort object. It’s important to use the unsafe(…) method.
- ✅ The JpaSort class extends Sort and inherits the **by**(…) method, so JpaSort.**by**(…) also returns only one Sort object. It’s important to use the unsafe(…) method.


### Chapter 8: Spring Data for NoSQL Databases

(No known issues)


### Chapter 9: Spring Web

#### @RequestMapping on Type

- ❌ @RequestMapping( "/api" ) public class StatisticRestController
- ✅ **@RestController**  @RequestMapping( "/api" ) public class StatisticRestController`

#### AuthenticationManager

- ❌ Then **,**, a special flag is set in the returned Authentication object, which signals that this user has been authenticated.
- ✅ Then, a special flag is set in the returned Authentication object, which signals that this user has been authenticated.

#### Summary

- ❌ Another exciting technology is GraphQL, which the Spring fro GraphQL project (https://spring.io/projects/spring-graphql) implements.
- ✅ Another exciting technology is GraphQL, which the Spring f**or** GraphQL project (https://spring.io/projects/spring-graphql) implements.


### Chapter 10: Logging and Monitoring

(No known issues)


### Chapter 11: Build and Deployment

(No known issues)

