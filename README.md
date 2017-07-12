Para montar las imágenes:

    docker build -t jtoledog/jenkins-slave jenkins-slave/.

    docker build -t jtoledog/jenkins-master jenkins-master/.

Para ejecutar los dockers:

    docker run -itd  -p 7022:22 --name=jenkins-esclavo jtoledog/jenkins-slave

    docker run -itd --name=jenkins-maestro --link jenkins-esclavo -p 7080:8080 -p 7050:50000 jtoledog/jenkins-master 