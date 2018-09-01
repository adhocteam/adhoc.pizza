pipeline {
  agent {
    label 'meatpillow'
  }

  stages {
    stage("Deploy") {
        when { branch 'master' }
        steps {
            sh 'aws s3 sync . s3://adhoc.pizza --exclude Jenkinsfile'
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