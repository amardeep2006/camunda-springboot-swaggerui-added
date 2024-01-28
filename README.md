# camunda-springboot-swaggerui-added
Sample project showcase on how to add swaggerui in Camunda

1. Download the camunda-engine-rest-openapi-7.XX.X.jar from https://artifacts.camunda.com/ui/native/camunda-bpm/org/camunda/bpm/camunda-engine-rest-openapi/ Download the Jar version same as Caunda version you plan to use.
  
2. Unzip this Jar using 7zip or any other tool. You will find a file openapi.json inside it. This contains the OPENAPI specs for Camunda.
   
3. Paste openapi.json inside src\main\resources\static folder of your project.
Add following dependency in your pom.xml
```xml
    <dependency>
      <groupId>org.springdoc</groupId>
      <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
      <version>2.3.0</version>
    </dependency>
```
Check the latest version of library whenever you are reading this.

4. Add following configuration in your application.yml

```yaml
springdoc:
  api-docs:
    enabled: true
  swagger-ui:
    url: /openapi.json
    path: /swaggerui
```

That’s it. Now swagger ui is accessible at http://localhost:8080/swaggerui
