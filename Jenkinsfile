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
        stage('deloy to tomcat') {
            steps {
               
               bat "copy target\\todo.war \".war\""
                }
            }        
        }
               
                
    }
