pipeline
 {
    agent any

    stages 
{
        stage ('Compile Stage') 
{

            steps
 {
                withMaven(maven : 'maven_3_5_0')
 {
                    sh 'mvn -f /var/lib/jenkins/workspace/jobdeclrative/pom.xml clean install'
                }
            }
        }

        stage ('Testing Stage')
 {

            steps
 {
                withMaven(maven : 'maven_3_5_0') 
{
                    sh 'mvn test'
                }
            }
        }
        stage('Deploy to Tomcat')
{
        steps
 {
        sh 'cp -r /root/.jenkins/workspace/vasaviproj/target/* /opt/apache-tomcat-8.5.29/webapps/'
        }
        }


        
    }
}
