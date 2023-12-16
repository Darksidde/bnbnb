pipeline {
    agent any

    tools {
        maven 'Maven' // Jenkins arayüzünde tanımlı Maven aracının adı
    }

    stages {
        stage('Build') {
            steps {
                script {
                    def mvnHome = tool name: 'Maven', type: 'maven'
                    sh "${mvnHome}/bin/mvn clean install" // Proje derleme işlemi
                }
            }
        }

        stage('Run TestNG Tests') {
            steps {
                script {
                    def mvnHome = tool name: 'Maven', type: 'maven'
                    sh "${mvnHome}/bin/mvn test" // TestNG testlerini çalıştırma işlemi
                }
            }
        }

        // Diğer aşamalar eklenebilir
    }
    // Post veya diğer seçenekler buraya eklenebilir
}
