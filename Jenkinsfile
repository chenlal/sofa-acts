pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('deploy') {
      steps {
        sh '''cp *.jar /var/jenkins /var/jenkins_home
'''
        sh 'java -jar -Xms1024m -Xmx1024m  *.jar > catalina.out &'
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

  }
}