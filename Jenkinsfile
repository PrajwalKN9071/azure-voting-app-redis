/*pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build') {
         steps {
            echo "one"
            pwsh(script: 'docker images -a')
            echo "two"
            pwsh(script: """
               cd azure-vote\
               docker images -a
               docker build -t jenkins-pipeline .
               docker images -a
               cd ..
            """)
            echo "three"
         }
      }
   }
}*/

pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository
                git url: 'https://github.com/PrajwalKN9071/azure-voting-app-redis', branch: 'main'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    def dockerImage = docker.build('jenkinspipeline:tag', '.')
                }
            }
        }
    }
}


