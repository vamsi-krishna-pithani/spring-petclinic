    pipeline {
        agent any
        stages {
            stage('vcs') {
                steps {
                git url : "https://github.com/vamsi-krishna-pithani/spring-petclinic.git",
                    branch : main
                }
            }
            stage("build & SonarQube analysis") {
                steps {
              withSonarQubeEnv('My SonarQube Server') {
                 sh 'mvn clean package sonar:sonar'
                }
              }    
            }
      
 
            
            stage('build') {
                steps {
                    sh "mvn package"

                }
            }
        }
    }