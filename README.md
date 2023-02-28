# hellonode

If the local user has a problem with premition to docker? then:
usermod -aG docker jenkins
usermod -aG root jenkins
chmod 664 /var/run/docker.sock

If you want to run jenkins in docker container and have an access to docker from container, you should to change access to directory with docker
chmod 664 /var/run/docker.sock or chmod 777 /var/run/docker.sock.


docker run -p 8080:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):/usr/bin/docker -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11
