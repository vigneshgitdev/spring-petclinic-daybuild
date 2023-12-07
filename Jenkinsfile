pipeline {
    agent { label 'MAVENMAVEN_3.9.6' }
    options { 
        timeout(time: 30, unit: 'MINUTES') 
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('git') {
            steps {
                git url: 'https://github.com/dummyrepos/spring-petclinic-nov23.git', 
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