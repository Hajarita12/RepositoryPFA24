FROM openjdk:17-jdk-alpine

# Copier le fichier JAR dans l'image
COPY target/pfa2021-0.0.1-SNAPSHOT.jar app.jar

# Point d'entrée pour l'exécution de l'application
ENTRYPOINT ["java", "-jar", "/app.jar"]
