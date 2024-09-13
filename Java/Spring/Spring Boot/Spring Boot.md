
Spring Boot is a collection of tools that extends the Spring framework and makes it easier to build applications quickly. It is used to build stand alone production ready spring applications.

https://start.spring.io/ initialises spring Boot applications.

- [[Inversion of Control]]
- [[Starting A Spring Boot Application]]
- [[@Autowire vs Constructor Injection]]
- [[Spring Bean]]
- [[Spring Bean Scope]]
-  [[Spring Controller]]
- [[Spring Data JPA]]
- [[Spring Profile]]


# Overview
**How are our requests handled?**
DispatcherServlet - Front Controller Pattern

The Dispatcher Servlet is the first thing your request go through, regardless of the URL you are making use of.

This is because it is mapped to the root URL '/'.

It then maps the request to the correct controller.

The dispatcher servlet is automatically configured by DispatcherServletAutoConfiguration

**How do Response objects get converted to JSON?**
@ResponseBody -> automatically serializes from object to JSON. 

@RestController uses both the annotation @Controller and @ResponseBody.

auto configured -> JacksonHttpMessageConverters is the default converter used by spring.

**What is configuring error mapping?**
Auto configuration using ErrorMVCAutoConfiguraation is used when an unknown url is typed.

**How are alll the jars available to us?
