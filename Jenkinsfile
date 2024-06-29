pipeline {
    agent any
    
    environment {
        SCANNER_HOME = tool 'sonar-scanner'
    }

    stages {
        stage('clone') {
            steps {
                git branch: 'main', credentialsId: 'git-cred', url: 'https://github.com/cxharles/10-Tier-x86_64.git'
            }
        }
        stage('sonarqube') {
            steps {
                withSonarQubeEnv('sonar') {
                   sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectKey=10-Tier -Dsonar.projectName=10-Tier -Dsonar.java.binaries=. '''
               }
            }
        }
        stage('adservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/adservice') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/adservice:latest .'
                          sh 'docker push charlesjatto/adservice:latest'
                          sh 'docker rmi charlesjatto/adservice:latest'
                      }
                   }
                }
            }
        }
        stage('cartservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/cartservice/src') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/cartservice:latest .'
                          sh 'docker push charlesjatto/cartservice:latest'
                          sh 'docker rmi charlesjatto/cartservice:latest'
                      }
                   }
                }
            }
        }
        stage('checkoutservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/checkoutservice') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/checkoutservice:latest .'
                          sh 'docker push charlesjatto/checkoutservice:latest'
                          sh 'docker rmi charlesjatto/checkoutservice:latest'
                      }
                   }
                }
            }
        }
        stage('currencyservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/currencyservice') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/currencyservice:latest .'
                          sh 'docker push charlesjatto/currencyservice:latest'
                          sh 'docker rmi charlesjatto/currencyservice:latest'
                      }
                   }
                }
            }
        }
        stage('emailservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/emailservice') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/emailservice:latest .'
                          sh 'docker push charlesjatto/emailservice:latest'
                          sh 'docker rmi charlesjatto/emailservice:latest'
                      }
                   }
                }
            }
        }
        stage('frontend') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/frontend') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/frontend:latest .'
                          sh 'docker push charlesjatto/frontend:latest'
                          sh 'docker rmi charlesjatto/frontend:latest'
                      }
                   }
                }
            }
        }
        stage('loadgenerator') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/loadgenerator') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/loadgenerator:latest .'
                          sh 'docker push charlesjatto/loadgenerator:latest'
                          sh 'docker rmi charlesjatto/loadgenerator:latest'
                      }
                   }
                }
            }
        }
        stage('paymentservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/paymentservice') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/paymentservice:latest .'
                          sh 'docker push charlesjatto/paymentservice:latest'
                          sh 'docker rmi charlesjatto/paymentservice:latest'
                      }
                   }
                }
            }
        }
        stage('productcatalogservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/productcatalogservice') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/productcatalogservice:latest .'
                          sh 'docker push charlesjatto/productcatalogservice:latest'
                          sh 'docker rmi charlesjatto/productcatalogservice:latest'
                      }
                   }
                }
            }
        }
        stage('recommendationservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/recommendationservice') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/recommendationservice:latest .'
                          sh 'docker push charlesjatto/recommendationservice:latest'
                          sh 'docker rmi charlesjatto/recommendationservice:latest'
                      }
                   }
                }
            }
        }
        stage('shippingservice') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'DockerHubCredentials', variable: 'DockerHubCredentials')]) {
                       dir('/var/lib/jenkins/workspace/10-Tier/src/shippingservice') {
                          sh 'docker login -u charlesjatto -p ${DockerHubCredentials}'
                          sh 'docker build -t charlesjatto/shippingservice:latest .'
                          sh 'docker push charlesjatto/shippingservice:latest'
                          sh 'docker rmi charlesjatto/shippingservice:latest'
                      }
                   }
                }
            }
        }
        stage('k8s-deployment') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'minikube', contextName: '', credentialsId: 'k8-cred', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://127.0.0.1:32769') {
                   sh "kubectl apply -f deployment-service.yml"
                   sh "kubectl get pods"
                   sh "kubectl get svc"
               }
            }
        }
    }
    post {
    always {
        script {
            def jobName = env.JOB_NAME
            def buildNumber = env.BUILD_NUMBER
            def pipelineStatus = currentBuild.result ?: 'UNKNOWN'
            def bannerColor = pipelineStatus.toUpperCase() == 'SUCCESS' ? 'green' : 'red'

            def body = """
                <html>
                <body>
                <div style="border: 4px solid ${bannerColor}; padding: 10px;">
                <h2>${jobName} - Build ${buildNumber}</h2>
                <div style="background-color: ${bannerColor}; padding: 10px;">
                <h3 style="color: white;">Pipeline Status: ${pipelineStatus.toUpperCase()}</h3>
                </div>
                <p>Check the <a href="${BUILD_URL}">console output</a>.</p>
                </div>
                </body>
                </html>
            """
           
           emailext (
                subject: "${jobName} - Build ${buildNumber} - ${pipelineStatus.toUpperCase()}",
                body: body,
                to: 'jattocharles777@gmail.com',
                from: 'jenkins@example.com',
                replyTo: 'jenkins@example.com',
                mimeType: 'text/html',
                attachmentsPattern: 'trivy-image-report.html'
            )
        }
    }
}
}
