pipeline {
    anyagent
    stages  {
         stage ('clone my code'){
           git 'https://github.com/kulmilind/maven-project'
           }
         stage ('compile my code'){
         
           steps {
               withmaven(maven : 'LocalMaven'){
                    sh 'mvn compile'
                    }
                    }
                    }
                    }
                    }
