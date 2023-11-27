node {
   
   //Declare a global variable for mvnHome

   stage('Version') { 

	  //build job: 'Version Check'
          
   }

   stage('Environment') {
       
       // build job: 'Enviro-Check'
       
   }

   //stage('Document') {
   
	  //build job: 'Generate-JavaDoc', parameters: [booleanParam(name: 'generate_javadoc', value: false), stringParam(name: 'javadoc_location', value: 'C:\\_javadoc00')]

   //}
	
   //stage ('Unit Test') {
	//git 'https://github.com/MarioRyanGreg/rock-paper-scissors.git'
	//bat "mvn clean test"
   //}
	
   stage('Build & Unit Test') {
       //git 'https://github.com/MarioRyanGreg/rock-paper-scissors.git'
       bat "mvn -Dmaven.test.failure.ignore=false clean package"
   }

   stage('Document') {
   
	  //build job: 'Generate-JavaDoc', parameters: [booleanParam(name: 'generate_javadoc', value: false), stringParam(name: 'javadoc_location', value: 'C:\\_javadoc00')]
	bat "mvn clean javadoc:javadoc"
   }
   
   stage('Acceptance') {
       
         //def response = input message: 'UAT Tests',   parameters: [choice(choices: 'Pass\nFail', description: 'Proceed or Abort?', name: 'Pass or Fail?')]

   }
   
   stage('Almost Done!') {
      def response = input message: 'Whatcha think?', parameters: [choice(choices: 'Yes\nNo', description: 'Proceed or Abort?', name: 'Wasn\'t that cool?')]
        
      if (response=="Yes") {
         echo "I agree!"
      } else {
         echo "You are hard to please."
      }
   }
	
   stage('Static Code Analysis'){
       build job: 'static-code-analysis'
   }
}
