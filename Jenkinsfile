
pipeline {
        agent any

        stages {
            stage('Checkout') {
                steps {
                                checkout scm                            }
                    }
                stage('Build') {
                steps {
                                sh ('/home/sai/distros/apache-maven-3.6.0/bin/mvn install')
                }
                }
                stage('Deployment') {
                      steps {
                            sh 'sshpass -p "123" scp target/gamutkart.war satya@172.17.0.3:/home/satya/distros/apache-tomcat-8.5.35/webapps'                    }
                 }
                 stage('Startup') {
			steps {
			   sh 'sshpass -p "123" ssh satya@172.17.0.3  /home/satya/distros/apache-tomcat-8.5.35/bin/startup.sh'
                 }
                 }
        }
}

