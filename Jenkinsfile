pipeline {
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
}
