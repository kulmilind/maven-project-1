pipeline {
    agent any
    
    stages  {
        stage ('clone my code'){
          git 'https://github.com/kulmilind/maven-project'
           }
    }
    {
         stage ('Compile Stage'){
             
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
  sshagent (['tomcat']) {
    sh 'ssh -o StrictHostKeyChecking=no */target/*.war ec2-user@52.90.76.47:/var/lib/tomcat/webapps'
  }
  }
            }
        
        
    }
}
                    
                    
