pipeline {
    agent any
    stages {
        stage('git') {
            steps {
              script {
                    git branch: 'main',
                        credentialsId: 'Github',
                        url: 'https://github.com/tpradeepgithub/Jenkin_Task2'
                }
            }
        }
      stage('build'){
        steps{
          sh '.\Sample.sh'
        }
      }
    }
    post {
        always {
            mail to: 'pradeep12798k@gmail.com',
                 subject: "Build Status: ${currentBuild.currentResult}",
                 body: "Build ${env.BUILD_NUMBER} finished with status: ${currentBuild.currentResult}"
        }
    }
}
.
