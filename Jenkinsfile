pipeline { 
    agent any 
    stages {
        stage('Build') { 
            steps {
                withMaven(maven : 'apache-maven-3.3.9', mavenSettingsConfig: 'settings.xml'){
                        bat "mvn clean compile"
                }
            }
        }
        stage('Test'){
            steps {
                withMaven(maven : 'apache-maven-3.3.9'){
                        bat "mvn test"
                }

            }
        }
    }
}
