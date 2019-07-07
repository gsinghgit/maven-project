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
        stage ('Deploy Stage') {
          
            steps {
    sshagent (credentials: ['049815be-e736-4389-83ff-f8f0be109ead']) {
    sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@54.157.142.126:/var/lib/tomcat/webapps '
}
}
}
}
