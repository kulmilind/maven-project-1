pipeline {
    agent any
    stages  {
        stage ('clone my code'){
          git 'https://github.com/kulmilind/maven-project'
           }
    }
    {
         stage ('compile my code'){
         
           steps {
               withmaven(Maven : 'LocalMaven'){
                    sh 'mvn clean compile'
                    }
                    }
                    }
                    }
                    }
