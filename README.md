# Complete-CI-CD-pipeline
pipeline {  agent any  environment {  DOCKER_IMAGE = "myrepo/devops-app"  }  stages {  stage('Checkout') {  steps {  git branch: 'main', url: 'https://github.com/user/project.git'  }  }  stage('Build') {  steps {  sh 'docker build -t $DOCKER_IMAGE .'  }  }  stage('Unit Test') {  steps {  sh 'pytest'  }  }  stage('SonarQube Scan') {  steps {  withSo
