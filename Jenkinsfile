pipeline {
  agent {
    label 'meatpillow'
  }

  stages {
    stage("Deploy") {
        when { branch 'master' }
        steps {
            sh 'aws s3 cp --exclude Jenkinsfile s3://adhoc.pizza .'
        }
    }
  }

  post {
    always {
      deleteDir()
      cleanWs()
    }
  }
}