pipeline
{
    agent {
  label {
    label 'DevServer'
    retries 2
  }
}

parameters {
  string defaultValue: 'S', name: 'LASTNAME'
}

environment {
    NAME = Ganesh
}

tools {
    maven 'mymaven'
}
stages {
    stage ('build')
    {
        steps {
            sh 'mvn clean package'
            echo "Hello $NAME ${params.LASTNAME}"
        }
        post {
        success {
            archiveArtifacts artifacts: '**/target/*.war'
            }
        }

    }
}
}