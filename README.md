# DockerTest
Ubuntu 18.04, Apache Maven 3.3.9, OpenJDK 8, git - proof of concept

docker build -t="dockerfile/maven" https://github.com/molbalazs/DockerTest.git

docker run -ti dockerfile/maven bash
