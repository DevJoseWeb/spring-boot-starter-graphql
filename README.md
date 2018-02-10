# Spring Boot Starter GraphQL

Bringing GraphQL goodness to Spring Boot applications. 

This project is based on the fine work made by the folks behind the [graphql-java](https://github.com/graphql-java/graphql-java) library.

**Note**: To support GraphQL's [subscriptions](http://graphql.org/blog/subscriptions-in-graphql-and-relay/) feature this module depends on Spring 5's WebFlux module and therefore Spring Boot 2.

# Maven

```
<dependency>
  <groupId>com.creactiviti</groupId>
  <artifactId>spring-boot-starter-graphql</artifactId>
  <version>0.0.1-SNAPSHOT</version>
</dependency>

<repositories>
   <repository>
      <id>maven-snapshots</id>
      <url>http://oss.sonatype.org/content/repositories/snapshots</url>
      <layout>default</layout>
      <releases>
         <enabled>false</enabled>
      </releases>
      <snapshots>
         <enabled>true</enabled>
      </snapshots>
   </repository>
</repositories>
```

# Kicking the tires

`spring-boot-starter-graphql` comes with a built in `ping` query to test that everything is fine:

```
curl -X POST -H "Content-Type:application/json" -d '{"query":"{ping}"}' http://localhost:8080/graphql
```

# Your first GraphQL Query

```
@Component
public class HelloWorld implements QueryBuilder {

  @Override
  public void build (Builder aBuilder) {
    aBuilder.field(Fields.field("hi")
                         .type(Scalars.GraphQLString)
                         .staticValue("Hello World"));
  }

}
```
