pipeline{
agent any
  tools{
    gradle('Gradle-6') 
    nodejs ('NodeJS20')
    }
  
stages{
  stage('Clone repository'){
    steps{
        echo 'Cloning repository'
        git'https://github.com/uncleNzia/gallery.git'
  }
  }
  stage('Build') {
      steps{
          sh npm install
          sh npm build
          echo 'Building app'
      }
    }
stage('Test') {
      steps{
          echo 'Testing app'
          sh 'gradle test'
      }
    }
stage('Deploy') {
      steps{
        echo 'Deploying app'
      }
    }
  stage('Slack'){
      steps {
        slackSend: 'app build message'
        }
    }
  post {
      always{
        echo 'auto-generated'
        emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Build failed'
        }
    }
}
}
