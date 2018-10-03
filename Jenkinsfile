pipeline {
  agent {
    label 'website'
  }

  stages {
    stage("Deploy") {
        when { branch 'master' }
        steps {
            sh 'aws s3 sync . s3://adhoc.pizza --exclude ".git/*" --exclude "Jenkinsfile" --delete --acl public-read'
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
