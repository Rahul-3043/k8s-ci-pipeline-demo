pipeline {

  agent {
    kubernetes {
      yamlFile 'k8s-agent.yaml'
    }
  }

  parameters {
    choice(name: 'LANGUAGE_STAGE', choices: ['node', 'python', 'docker'], description: 'Select which stage to run')
  }

  stages {

    stage('Node Stage') {
      when {
        expression { params.LANGUAGE_STAGE == 'node' }
      }
      steps {
        container('node') {
          sh 'node -v'
        }
      }
    }

    stage('Python Stage') {
      when {
        expression { params.LANGUAGE_STAGE == 'python' }
      }
      steps {
        container('python') {
          sh 'python --version'
        }
      }
    }

    stage('Docker Stage') {
      when {
        expression { params.LANGUAGE_STAGE == 'docker' }
      }
      steps {
        container('docker') {
          sh 'docker --version'
        }
      }
    }

  }
}
