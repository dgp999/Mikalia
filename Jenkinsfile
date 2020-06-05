pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn clean install package'
      }
    }

    stage('analysis') {
      steps {
        withSonarQubeEnv(installationName: 'withSonarQubeEnv', credentialsId: 'SonarQube-Server')
        sh 'mvn sonar:sonar -Dsonar.host.url=http://http://13.235.254.100:9000/sonar/ -Dlicense.skip=true'
      }
    }

  }
}