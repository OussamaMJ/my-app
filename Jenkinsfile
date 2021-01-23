node{
  stage("SCM Checkout"){
    git 'https://github.com/OussamaMJ/my-app'
  }
  
  stage("Compile-Package"){
    sh 'mvn package'
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
