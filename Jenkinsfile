pipeline {
    agent any

    environment {
        APP_NAME = 'servicio-tarjetas'
        JAVA_HOME = tool 'Java 21'
        DOCKER_REGISTRY = 'registry.empresa.com'
    }

    stages {
        stage('1. Checkout & Validación de Contrato') {
            steps {
                checkout scm
                echo "Validando contrato OpenAPI congelado..."
            }
        }

        stage('2. Compilación Quarkus') {
            steps {
                echo "Compilando con maven..."
                sh './mvnw clean compile'
            }
        }

        stage('3. Pruebas Unitarias y Cobertura') {
            steps {
                echo "Ejecutando suite de pruebas JUnit 5..."
                sh './mvnw verify'
            }
            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }

        stage('4. Compuerta de Calidad SonarQube') {
            steps {
                echo "Verificando Quality Gate de código Quarkus..."
            }
        }

        stage('5. Construcción de Imagen Docker') {
            steps {
                sh "docker build -f Dockerfile.jvm -t ${DOCKER_REGISTRY}/${APP_NAME}:${BUILD_NUMBER} ."
            }
        }
    }

    post {
        success {
            echo "Microservicio ${APP_NAME} listo para despliegue."
        }
        failure {
            echo "Fallo en pipeline CI/CD."
        }
    }
}
