Spring Bean has many scopes. every scope decide how many instances of that class (Bean instance) will be created and used.

Bean will be valid for...

| Scope          | Description                                                                  |
| -------------- | ---------------------------------------------------------------------------- |
| Singleton      | Single instance per Spring IoC container (default).                          |
| Prototype      | This scopes a single bean definition to have any number of object instances. |
| Request        | This scopes a bean definition to an HTTP request.                            |
| Session        | This scopes a bean definition to an HTTP session.                            |
| Global-session | This scopes a bean definition to a global HTTP session.                      |

