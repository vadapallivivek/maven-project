pipeline 
{
    agent any
    stages{
        stage('Build'){
	   steps {	
	   	def mvn_version = 'localmaven'
           	withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ){	
                	sh 'mvn clean package'
            	}
           }
	   post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}

