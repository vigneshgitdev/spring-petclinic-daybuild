pipeline {
    agent { label "MAVEN_3.9.6"}
    options {
         timeout(time: 30, unit: 'MINUTES')
    }
    trigger {
        pollSCM('* * * * *')
    }
    stages {
        stage (git) {
            step {
                git url : 
                branch : dev

            }
        }
        stage (build) {
            step {
                sh "mvn clean package"
            }
        }
    }
 }