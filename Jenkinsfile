node('built-in') 
{
    stage('ContinousDownload')
        {
	     git branch: 'main', url: 'https://github.com/sumanthintime/maven.git'
	         }
		     stage('ContinousBuild')
		         {
			      sh 'mvn package'
			          }
				      stage('Contionous Deploy')
				          {
					         deploy adapters: [tomcat9(credentialsId: 'e076cc35-1738-42ec-8b34-cf8eef122809', path: '', url: 'http://172.31.4.250:8080')], contextPath: 'testapp', war: '**/*.war'
						     }
						         stage('ContionousTesting')
							     {
							            git branch: 'main', url: 'https://github.com/sumanthintime/FunctionalTesting.git'
								           sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
									       }
									           stage('ContionousDelivery')
										       {
										              deploy adapters: [tomcat9(credentialsId: 'e076cc35-1738-42ec-8b34-cf8eef122809', path: '', url: 'http://18.144.66.195:8080')], contextPath: 'prodapp', war: '**/*.war'
											          }
												  }




