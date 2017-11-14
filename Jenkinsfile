pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }

        stage('Run') {
            steps {
                sh 'ls'
                sh 'java -jar target/test-1.5.8.RELEASE.jar'
                sh 'docker run -v /target:/target --rm dockerfile/java:oracle-java8 java -jar /target/test-1.5.8.RELEASE.jar
            }
        }
    }
}