  
pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven3"
    }

    stages {
        
stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('sq') {
                 
                  bat 'mvn sonar:sonar -Dsonar.login=a9f1b2f450793f58d6ced555e121235e36e4c0d3 -D.host.url=http://localhost:9000/ ' 
                   
                       
                    }
                }
            }

    }
}
