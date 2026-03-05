pipeline {
    agent {
        kubernetes {
            yamlFile 'k8s-agent.yaml'
        }
    }

    stages {

        stage('Node Stage') {
            steps {
                container('node') {
                    sh 'node -v'
                }
            }
        }

        stage('Python Stage') {
            steps {
                container('python') {
                    sh 'python --version'
                }
            }
        }

        stage('Docker Stage') {
            steps {
                container('docker') {
                    sh 'docker version'
                }
            }
        }

        stage('Helm Stage') {
            steps {
                container('helm') {
                    sh 'helm version'
                }
            }
        }

        stage('Kubectl Stage') {
            steps {
                container('kubectl') {
                    sh 'kubectl version --client'
                }
            }
        }

    }
}
