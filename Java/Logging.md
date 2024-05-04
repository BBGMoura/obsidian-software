The library we can use for logging is called Simple Logging Façade for Java (SLF4J )with Log back.

Logging is just printing information to a file system.
## Log Levels
In order of information levels:
- DEBUG
- INFO
- WARNING
- ERROR

Generally these are the levels logs are active on:
- Debug -> local
- Info -> Test
- Warning -> Acceptance + Prod

The Spring Boot  start web dependency includes the dependencies for:
- logback
- slf4