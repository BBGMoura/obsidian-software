``` java
public class AuthorizationException extends RuntimeException {
	private final ErrorCode;

	public AuthorizationException(String message, ErrorCode error) {
		super(message);
		this.error = error;
	}

	public AuthorizationException(String message, Throwable cause, ErrorCode error) {  
	    super(message, cause);  
	    this.error = error;  
	}
}
```

```java
public class EmptyStackException extends RuntimeException {
      public EmptyStackException() {
          super();
      }
      public EmptyStackException(String s) {
          super(s);
      }
      public EmptyStackException(String s, Throwable throwable) {
          super(s, throwable);
      }
      public EmptyStackException(Throwable throwable) {
          super(throwable);
      }
    }
```


