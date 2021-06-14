pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven3"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/mndp1234/todo-app.git'

                // Run Maven on a Unix agent.
                
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
                
                sh "mvn clean install"               

                // To run Maven on a Windows agent, use
                
            }

           
        }
        
        
stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('sq') {
                 
                  bat 'mvn sonar:sonar \
  -Dsonar.projectKey=com.mtodo \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=a9f1b2f450793f58d6ced555e121235e36e4c0d3 ' 
                   
                       
                    }
                }
            }


        stage('Deploy to Tomcat'){steps{
     bat "copy target\\todo-app.war \"webapps.war\""}
        }
    }
               
                
    }
