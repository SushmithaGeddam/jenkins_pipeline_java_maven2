node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   
   git url: 'https://github.com/SushmithaGeddam/jenkins_pipeline_java_maven2.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'Maven-3.5.0'
   //def javaHome = tool 'JAVA_HOME'

bat "$mvnHome/bin/mvn install"

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   bat "${mvnHome}\\bin\\mvn -Dmaven.test.failure.ignore clean package"
   step([$class: 'JUnitResultArchiver', testResults: '**\\target\\surefire-reports\\TEST-*.xml'])
}
