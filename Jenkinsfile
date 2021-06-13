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
                
                bat "mvn -Dmaven.test.failure.ignore=true clean package"
                
                bat "mvn clean install"               

                // To run Maven on a Windows agent, use
                
            }

           
        }
        stage('deloy to tomcat') {
            steps {
               
              bat 'scp -o StrictHostKeyChecking=no target/*.war navdeep@127.0.0.1:D:/neeraj/'
                }
            }        
        }
               
                
    }
