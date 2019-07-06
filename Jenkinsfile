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
    }
}
                    
                    
