node{
  stage("SCM Checkout"){
  git 'https://github.com/OussamaMJ/my-app'
  }
  
  stage("Compile-Package"){
    sh 'mvn package'
  }
}
