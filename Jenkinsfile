node{
  stage("SCM Checkout"){
    git 'https://github.com/OussamaMJ/my-app'
  }
  
  stage("Compile-Package"){
    sh 'mvn package'
  }
  
  stage('SonarQube analysis') {
    withSonarQubeEnv('sonar_demo') {
      sh "mvn sonar:sonar"
  }
  }
  
  stage("Quality Gate Check"){
          timeout(time: 1, unit: 'HOURS') {
              def qg = waitForQualityGate()
              if (qg.status != 'OK') {
                  error "Pipeline aborted due to quality gate failure: ${qg.status}"
              }
          }
  }   
    
  stage("Sending Emails"){
    mail bcc: '', 
    body: '''Hello This is a Jenkins Email Alert Thanks''', 
    cc: '', 
    from: '', 
    replyTo: '', 
    subject: 'Jenkins Email', 
    to: 'oussama.mjihil@gmail.com'
  }
}
