pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "mymaven"
        jdk   "myjava"
    }

    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/edureka-git/DevOpsClassCodes.git'
            }
        }
            
            stage('compile'){
                  
                  steps {
                    sh 'mvn compile'
                      
                  }
            }
            
            stage('Codereview'){
                
                steps {
                   
                   sh 'mvn pmd:pmd' 
                }
            }
            
            stage('Unit test'){
                
                steps{
                    sh 'mvn test'
                }
            }
            
            stage('MetricCheck')
            {
                steps{
                    sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
                }
            }
            stage('package')
            {
               
                steps{
                    sh 'mvn package'
                }
            }
            }

            
        }
