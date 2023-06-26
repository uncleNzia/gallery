pipeline{
agent any
stages{
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
      }
    }
stage('Deploy') {
      steps{
        echo 'Deploying app'
      }
    }
}
}
