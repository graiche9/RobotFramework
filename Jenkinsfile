pipeline {
    agent {
        docker {
            image 'python:3.9-slim'
        }
    }

    environment {
        SELENIUM_GRID_URL = "http://192.168.1.22:4444"
    }
    stages {
        stage('Install python'){
                steps {
                //sh'pip freeze > requirements.txt'
                //sh ' python3 -m pip install -r requirements.txt'
                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install -r requirements.txt
                '''
            }
        }
    
    stage('Run Selenium Tests') {
            steps {
                // Exécution des tests avec Selenium
                sh  'python3 -m robot tests/login_avec_template_data.robot'
            }
    }
    }

}