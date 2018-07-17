[参考链接](http://www.baeldung.com/swagger-2-documentation-for-spring-rest-api)

## 首先你得有个 Rest 风格的项目

## 添加依赖

找到项目的 pom.xml 文件在依赖中添加

```java
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger2</artifactId>
    <version>2.7.0</version>
</dependency>
```

## 将 Swagger 2 整合到项目中

新建一个java类

```java
@Configuration
@EnableSwagger2
public class SwaggerConfig {                                    
    @Bean
    public Docket api() { 
        return new Docket(DocumentationType.SWAGGER_2)  
          .select()                               
          .apis(RequestHandlerSelectors.any())   
          .paths(PathSelectors.any())             
          .build();                                           
    }
}
```

## 验证是否添加成功

为了验证 Springfox 是否有效，在浏览器中登录下面的网址进行验证。

http://localhost:8080/v2/api-docs

如果页面显示出许多的键值对则说明添加成功

## Swagger UI

在项目的 Maven 依赖中添加

```java
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger-ui</artifactId>
    <version>2.7.0</version>
</dependency>
```

为了测试是否有效，在浏览器中输入以下网址进行测试

http://localhost:8080/swagger-ui.html 

至此，整合完毕剩下的就需要继续探索了。