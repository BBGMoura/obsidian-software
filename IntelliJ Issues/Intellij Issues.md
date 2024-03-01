### Issue 1 - using Gradle not Maven
When running tests, the following issue is concurring:
```
Can't get the delegate of the gradle IncrementalProcessingEnvironment.
```

Solution - 
Under _Settings -> Build, Execution, Deployment -> Build Tools -> Maven_ , select the checkbox which says _Delegate IDE build/run actions to Maven_.

![[Issue 1 - Use Maven instead of Gradle..png]]