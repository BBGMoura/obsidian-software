In order to interact with a keystore or truststore, you need the keytool found under the system-wide java path or java version that is bundled with your application.

Note: The keytool can be found in the bin directory where JAVA_HOME is your JDK Installation directory.

``` bash
export PATH=$JAVA_HOME/bin:$PATH 
keytool ...
```

By default, the keytool will generate a keystore in the user's home directory (Linux: `$HOME/.keystore`).

The Java keystore password is required and must be 6 characters or longer. Its value is `changeit` by default. It should be changed for security reasons

``` bash
# fully interactive 
$ $JAVA_HOME/bin/keytool -storepasswd -keystore /path/to/keystore.jks 
Enter keystore password: changeit 
New keystore password: new-password 
Re-enter new keystore password: new-password 

# or provide the new password directly as parameter 
# not recommended because the password can end up in the shell history 
$ $JAVA_HOME/bin/keytool -storepasswd -new NEWPASSWORD -storepass:env KEYSTORE_PASSWORD -keystore /path/to/keystore.jks
```

