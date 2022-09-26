pipeline{
    agent{label 'Tomcat'}
    tools {
        maven "maven-3.8.6"
        //jdk "openjdk 11.0.16 "
    }
    stages{
        stage('checkout'){
            steps{
                git 'https://github.com/Ajayshady/mvn_shoppingcart.git'
                
            }//steps
        }//stage
        stage('inisttilaise'){
        steps{
            echo "PATH=/opt/apache-maven-3.8.6/bin:$PATH"
        }//steps

        }//stage
        stage('build project'){ 
            steps{ 
               dir("/home/centos/workspace/shoppingcart") {
                sh "mvn clean package"
                }//block
            }//steps
        }//stage
        stage('copy war file to tomcat server'){
            steps{
                sh 'sudo cp  target/*.war  /opt/tomcat-9.0/webapps/'
            }//steps
        }//stage
    }//stages
}//pi
