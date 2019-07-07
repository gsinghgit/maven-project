pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/prakashk0301/maven-project'
        }
  }
    {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Test Stage') {

           steps {
               withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean test'
               }
           }
        }
        stage ('Package Stage') {

           steps {
               withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean package'
               }
           }
        }
        stage ('Install Stage') {

           steps {
               withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean install'
}
}
}
}
}
