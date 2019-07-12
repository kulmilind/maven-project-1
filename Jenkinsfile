pipeline {
    agent any
    
    stages  {
        stage ('clone my code'){
          git 'https://github.com/kulmilind/maven-project-1.git'
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
        
        
    }
}
                    
                    
