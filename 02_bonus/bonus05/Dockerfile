#mettre le fichier java ici
#docker build -t java-image .
#docker run -it --rm java-image

FROM java
COPY java /usr/src/project
WORKDIR /usr/src/project
RUN javac com/example/bbrunell/avajlauncher/Simulation.java
CMD ["bash", "-c", "java com.example.bbrunell.avajlauncher.Simulation scenary && bash"]