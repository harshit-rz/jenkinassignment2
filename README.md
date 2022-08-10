# jenkin assignment 2
pipeline script used for successful build:

pipeline {
 agent any
 environment {
  dotnet = 'C:/Program Files (x86)/dotnet/dotnet.exe'
 }
 stages {
  stage('Checkout') {
   steps {
    git url: 'https://github.com/harshit-rz/jenkinassignment2.git', branch: 'main'
   }
  }
  stage('Restore PACKAGES') {
   steps {
    bat "dotnet restore WebApplication1.sln"
   }
  }
  stage('Build') {
   steps {
    bat 'dotnet build --configuration Release'
   }
  }
   
 }
}
