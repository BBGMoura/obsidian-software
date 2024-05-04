This is used to build CI/CD pipeline. Utilises Docker to build and run tests.

Github Action workflow:
- Build & Test
- Build Docker image
- Push image to Docker Hub

Below is a script that does the above:
``` yml
name: Push CI/CD flow for booking-system  
  
on:  
  push:  
    branches: [ "master" ]  
  
jobs:  
  build_push_docker:  
  
    runs-on: ubuntu-latest  
  
    steps:  
      - uses: actions/checkout@v4  
      - name: Set up JDK 21  
        uses: actions/setup-java@v4  
        with:  
          java-version: '21'  
          distribution: 'temurin'  
          cache: maven  
      - name: Build with Maven  
        run: mvn clean install  
  
      - name: Build & Push Docker image  
        if: github.event_name == 'push'  
        uses: mr-smithers-excellent/docker-build-push@v6  
        with:  
          image: brunamoura/booking-system-image  
          tags: latest  
          registry: docker.io  
          dockerfile: Dockerfile  
          username: ${{ secrets.DOCKER_USERNAME }}  
          password:
```

The Dockerfile must be located in the root (same level as src):

``` dockerfile
FROM openjdk:21  
EXPOSE 8080  
ADD target/booking-system-image.jar booking-system-image.jar  
ENTRYPOINT ["java", "-jar","/booking-system-image.jar"]
```

It includes the `booking-system-image.jar`. This application has this name as we have added the fileName tag in the pom.xml file. Inside the `<build>`:

``` xml
<finalName>booking-system-image</finalName>
```

So the jar file generated in the target folder will have the name as above.