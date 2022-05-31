node {
    checkout scm

    def customImage = docker.build("hamza21/ripo-spring-boot-docker-compose:initial")

    customImage.inside {
        sh 'make test'
    }
}