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
                sh 'java -jar target/test-1.5.8.RELEASE.jar'
                //sh 'docker run -v /Users/shelajev/repo:/opt/repo -p 8080:8080 --rm dockerfile/java:oracle-java8 java -jar /opt/repo/tmp/gs-spring-boot/complete/target/gs-spring-boot-0.1.0.jar
                sh 'ls'
            }
        }
    }
}