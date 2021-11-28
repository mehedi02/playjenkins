pipeline {

  //agent { label 'kubepod' }
  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/mehedi02/playjenkins.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfigk8s")
        }
      }
    }

  }

}
