pipeline {
    agent any

    tools {
        // Maven aracını tanımla
        maven 'Maven' // 'Maven' burada tanımlı Maven aracının adıdır, Jenkins arayüzünde belirtilen isimle aynı olmalıdır
    }

    stages {
        stage('Build') {
            steps {
                // Tanımlanan Maven aracını çağırarak proje derleme işlemi
                script {
                    def mvnHome = tool name: 'Maven', type: 'maven'
                    sh "${mvnHome}/bin/mvn clean install" // Maven'in doğru sürümünü belirtin
                }
            }
        }

       stage('Run TestNG Tests') {
    steps {
        script {
            def mvnHome = tool name: 'Maven', type: 'maven'
            sh "${mvnHome}/bin/mvn test" // TestNG testlerini otomatik olarak algılar ve çalıştırır
        }
    }
}

        
        // Diğer aşamaları buraya ekleyebilirsiniz: test, dağıtım, vs.
    }
    // Post veya diğer seçenekleri de burada ekleyebilirsiniz.
}
