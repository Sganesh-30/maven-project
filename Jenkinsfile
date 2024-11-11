pipeline
{
    agent {
  label {
    label 'DevServer'
    retries 2
  }
}
tools {
    maven 'mymaven'
}
stages {
    stage ('build')
    {
        steps {
            sh 'mvn clean package'
        }
        post {
        success {
            archiveArtifacts artifacts: '**/target/*.war'
            }
        }

    }
}
}