node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   
   git url: 'https://github.com/SushmithaGeddam/jenkins_pipeline_java_maven2.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'Maven-3.5.0'
   //def javaHome = tool 'JAVA_HOME'

bat (/"C:\Program Files\apache-maven-3.5.0\bin\mvn" install/)
   //(/"D:\Apache\apache-maven-2.2.1\bin\mvn" clean package -Dmaven.test.skip=true -P oracle/) 

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
  // bat "${mvnHome}\\bin\\mvn -Dmaven.test.failure.ignore clean package"
 bat (/"C:\Program Files\apache-maven-3.5.0\bin\mvn" -Dmaven.test.failure.ignore clean package/)
  step([$class: 'JUnitResultArchiver', testResults: '**\\target\\surefire-reports\\TEST-*.xml'])
}
