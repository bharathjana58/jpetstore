pipeline {
   agent any
   tools
  {  
    jdk 'JAVA_HOME'
    maven 'MAVEN_HOME'
       }
      stages
	{
         stage('checkoutstage')
	{
	steps
	{
	  checkout scm
        }
      }
        stage('Build') 
	{
	 steps
         { 
            sh 'mvn clean package -DskipTests'
	     }
	  }
		stage('Jenkins-Node-slave') {
      steps {
        node('tomcat-node'){
         checkout scm
                 }
      }
    } 
	
    }
}
