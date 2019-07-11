pipeline {
    agent any
    
    stages  {
        stage ('clone my code'){
          git 'https://github.com/kulmilind/maven-project'
           }
    }
    {
         stage ('Compile Stage'){
             agent(label 'maven')
             steps {
               withMaven(maven : 'LocalMaven'){
                    sh 'mvn clean compile'
                    }
                    }
                    }
        stage ('Test Stage'){
            steps{
                withMaven(maven : 'LocalMaven'){
                    sh 'mvn test'
                }
            }
        }
      stage ('Install Stage'){
            steps{
                withMaven(maven : 'LocalMaven'){
                    sh 'mvn install'
                }
            }
      }
        stage ('deployment'){
            steps 
  {
  sshagent (credentials: ['8cb108d6-eb38-45a2-9736-0d3d841f3f13']) {
    sh 'ssh -o StrictHostKeyChecking=no */target/*.war ec2-user@3.83.98.162:/var/lib/tomcat/webapps'
  }
  }
            }
        
    }
}
                    
                    
