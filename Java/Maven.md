Maven is a Java application that solves project-level complexity problems. It does various things:
- installs third-party libraries
- defines standard project structure
- builds and executes the project in different modes
- bundles the project to be shared and deployed

It is a software project management and comprehension tool.

It is a command-line application for managing Java software projects.  Maven ...
- Can create a new Java project from a template. A Maven project template is called an **archetype**.
- Defines a consistent project structure which is recognised by all Java IDEs.
- Automatically downloads and installs third-party Java libraries from a central repository and makes them available to a project. There are currently 5,228,080 Java jars (bundled libraries) available.
- Compiles and tests Java projects
- Is extendable via plug-ins
## Defining Artefact Coordinates
- GroupId uniquely identifies an organisation or group within organisation. Naming convention: `some.package.name`
- ArtifactId identifies the project. Naming convention : `some-project-name`

## Maven Directory Structure
Maven defines a standard directory structure for both source code and compiled output. It is possible to modify the structure with the POM but there generally is no need. 

Standard structure:
```
learn-nlp
├───.idea             // IntelliJ project data
└───src
    ├───main          // Application
    │   ├───java      // Source code
    │   └───resources // Non-source files the application requires.
    └───test          // Test
        └───java      // Source code
```

## Dependencies
Maven's greatest superpower is its ability to fetch and install Java libraries that someone else created. Maven third-party libraries are called dependencies.

This is how to define a dependency in your pom.xml file:

``` xml
<dependencies>
	<dependency>  
	    <groupId>com.h2database</groupId>  
	    <artifactId>h2</artifactId>  
	    <scope>runtime</scope>  
	</dependency>
</dependencies>
```

## Maven Clean Install
When running `mvn clean install`, you are generating the items inside the target folder. You have the compile .class files inside the classes folder. 

In addition, you have the .jar file of the program. This is the file which is used to deploy. You can run the following command to run the program in the terminal :

``` shell
java -jar path/file-name-version.jar
```

In conclusion, `mvn clean install`  deletes the target folder if existing, compiles the .java files to .class files, packages a jar file, and stores it in the target folder.

