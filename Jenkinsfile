pipeline {
    agent { label 'MAVEN_3.9.6' }
    options { 
        timeout(time: 30, unit: 'MINUTES') 
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('git') {
            steps {
                git url: 'https://github.com/vigneshgitdev/spring-petclinic-daybuild.git', 
                    branch: 'dev'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }

}