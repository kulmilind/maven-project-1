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
  sshagent (['68b46f44-22d5-4eb0-87aa-23b5e52b32cc']){
    sh 'ssh -o StrictHostKeyChecking=no */target/*.war ec2-user@3.91.252.223:/var/lib/tomcat/webapps'
  }
  }
            }
        
        
    }
}
                    
                    
