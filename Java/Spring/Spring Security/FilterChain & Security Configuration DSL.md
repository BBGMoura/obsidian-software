Spring's DefaultSecurityFilterChain consists of 15 filters before it hits the controllers. The order is important: ![[Spring DefaultSecurityFilter.png]]


Some notable filters:

- **BasicAuthenticationFilter**: Tries to find a Basic Auth HTTP Header on the request and if found, tries to authenticate the user with the header’s username and password.

-  **UsernamePasswordAuthenticationFilter**: Tries to find a username/password request parameter/POST body and if found, tries to authenticate the user with those values.

- **DefaultLoginPageGeneratingFilter**: Generates a login page for you, if you don’t explicitly disable that feature. THIS filter is why you get a default login page when enabling Spring Security.

- **DefaultLogoutPageGeneratingFilter**: Generates a logout page for you, if you don’t explicitly disable that feature.

- **FilterSecurityInterceptor**: Does your authorisation.

These filters are Spring Security. They do all the work. What is left is for use to configure how they do their work, i.e. which URLs to protect, which to ignore and what database tables to use for authentication.


**This is for earlier versions before Spring Security 5.**
## Configuring Spring Security: WebSecurityConfigurerAdapter

The way to configure spring security is by having a class which:
- is annotated with @EnabledWebSecurity
- extends WebSecurityConfigurer, which offers configuration DSL/methods. These methods specify which URIs to protect or protections to enable/disable.

Example:

``` java
@Configuration
@EnableWebSecurity // (1)
public class WebSecurityConfig extends WebSecurityConfigurerAdapter { // (1)

  @Override
  protected void configure(HttpSecurity http) throws Exception {  // (2)
      http
        .authorizeRequests()
          .antMatchers("/", "/home").permitAll() // (3)
          .anyRequest().authenticated() // (4)
          .and()
       .formLogin() // (5)
         .loginPage("/login") // (5)
         .permitAll()
         .and()
      .logout() // (6)
        .permitAll()
        .and()
      .httpBasic(); // (7)
  }
}
```

1 ->  A normal Spring @Configuration with the @EnableWebSecurity annotation, extending from WebSecurityConfigurerAdapter.

2 -> By overriding the adapter’s configure(HttpSecurity) method, you get a nice little DSL with which you can configure your FilterChain.

3 -> 1. All requests going to `/` and `/home` are allowed (permitted) - the user does _not_ have to authenticate. You are using an [antMatcher](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/util/AntPathMatcher.html), which means you could have also used wildcards (*, \*\*, ?) in the string.

4 -> 1. Any other request needs the user to be authenticated _first_, i.e. the user needs to login.

5 -> You are allowing form login (username/password in a form), with a custom loginPage (`/login, i.e. not Spring Security’s auto-generated one).

6 -> The same goes for the logout page

7 -> you are also allowing Basic Auth, i.e. sending in an HTTP Basic Auth Header to authenticate.

### How to use Spring Security's configure DSL

_THIS_ `configure` method is where you specify:

1. What URLs to protect (authenticated()) and which ones are allowed (permitAll()).
2. Which authentication methods are allowed (formLogin(), httpBasic()) and how they are configured.
3. In short: your application’s complete security configuration.

The default adapter's configure method:

``` java
public abstract class WebSecurityConfigurerAdapter implements
		WebSecurityConfigurer<WebSecurity> {

    protected void configure(HttpSecurity http) throws Exception {
            http
                .authorizeRequests()
                    .anyRequest().authenticated()  // (1)
                    .and()
                .formLogin().and()   // (2)
                .httpBasic();  // (3)
        }
}
```

1 -> 1. To access _any_ URI (`anyRequest()`) on your application, you need to authenticate (authenticated()).

2 -> 1. Form Login (`formLogin()`) with default settings is enabled.

3 -> 1. As is HTTP Basic authentication (`httpBasic()`).



**Newer versions after Spring Security 5**

``` java
@Configuration  
@EnableWebSecurity  
@EnableMethodSecurity // Enables method-level security like @PreAuthorize  
public class SecurityConfig {  
  
    private final JwtAuthenticationFilter jwtAuthFilter;  
    private final AuthenticationProvider authenticationProvider;  
  
    @Bean  
    public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {  
        http.csrf(AbstractHttpConfigurer::disable) // Disable CSRF protection for stateless APIs  
            .authorizeHttpRequests(auth -> auth  
                    .requestMatchers("/auth/**",  
                                     "/swagger-ui/**",  
                                     "/v3/api-docs/**",  
                                     "/swagger-ui.html",  
                                     "/h2-console/**") // Public endpoints  
                    .permitAll()  
                    .requestMatchers("/admin/**") // Admin-specific endpoints  
                    .hasAuthority("ADMIN")  
                    .anyRequest() // All other requests  
                    .authenticated() // Must be authenticated  
            )  
            .headers(headers -> headers  
                    .frameOptions(HeadersConfigurer.FrameOptionsConfig::disable) // Allow iframe embedding for H2 console  
            )  
            .sessionManagement(session -> session  
                    .sessionCreationPolicy(SessionCreationPolicy.STATELESS) // Use stateless sessions  
            )  
            .authenticationProvider(authenticationProvider) // Custom authentication provider  
            .addFilterBefore(jwtAuthFilter, UsernamePasswordAuthenticationFilter.class); // JWT filter before default filter  
        return http.build();  
    }
```

