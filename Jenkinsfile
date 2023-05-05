pipeline {
  agent any

  stages {
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar'
            }
        }   
  stage('Docker build and Push') {
            steps {
              sh "printenv"
              sh "docker build -t mayowa2022/numeric-app:""$GIT_COMMIT"" "
              sh "docker push mayowa2022/numeric-app:""$GIT_COMMIT"" "
            }
        }   
    }
}